# ce-7.0

## Common Problems

### Not able to open Markdown file

If after upgrading to 7.0, you are not able to open Markdown file and if your seahub.log containing the following error, it is caused by you forgot to migrate file comment when you upgrade to 6.3 version.

![](https://download.seafile.com/lib/1bf61316-c5e2-44ab-88d9-a81c3b2b6890/file/images/auto-upload/image-1558745192334.png?raw=1)

<img src="https://download.seafile.com/lib/1bf61316-c5e2-44ab-88d9-a81c3b2b6890/file/images/auto-upload/image-1558745374080.png?raw=1" height="null" width="611.609375" />

You can delete the table base_filecomment and recreate the table.

```
CREATE TABLE `base_filecomment` (  
    `id` int(11) NOT NULL AUTO_INCREMENT,  `author` varchar(255) NOT NULL,  
    `comment` longtext NOT NULL,  `created_at` datetime NOT NULL,  
    `updated_at` datetime NOT NULL,  `uuid_id` char(32) NOT NULL,  
    `detail` longtext NOT NULL,  `resolved` tinyint(1) NOT NULL,  
    PRIMARY KEY (`id`),  KEY `base_filecomment_uuid_id_4f9a2ca2_fk_tags_fileuuidmap_uuid` (`uuid_id`),  
    KEY `base_filecomment_author_8a4d7e91` (`author`),  
    KEY `base_filecomment_resolved_e0717eca` (`resolved`),  
    CONSTRAINT `base_filecomment_uuid_id_4f9a2ca2_fk_tags_fileuuidmap_uuid` FOREIGN KEY (`uuid_id`) REFERENCES `tags_fileuuidmap` (`uuid`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

```




