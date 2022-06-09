**Arbitrary code execution vulnerability exists in ESPCMS management system**

 



**Vulnerability description:**

The vulnerability modifies the content of the homepage template file in the background, and after modification, a PHP suffix file with the same content will be generated. When the frontend accesses the homepage file, local code execution will be triggered.

**Supplier:** https://www.ecisp.cn/

**Vulnerability file:** 

espcms\espcms_public\espcms_templates\ESPCMS_Templates.php

**Code Analysis:**

The code execution function eval is called in line 165. The content obtained by the $out variable is the content of the template file. The $fetch_filename parameter in line 84 is actually the address of the template file. In line 90, it is simply obtained with the file_get_contents() function. The contents of the template file are then assigned to $out.

espcms\espcms_public\espcms_templates\ESPCMS_Templates.php
 ![img](file:///C:/Users/JeakinsCheung/AppData/Local/Packages/oice_16_974fa576_32c1d314_30a7/AC/Temp/msohtmlclip1/01/clip_image002.jpg)

![img](file:///C:/Users/JeakinsCheung/AppData/Local/Packages/oice_16_974fa576_32c1d314_30a7/AC/Temp/msohtmlclip1/01/clip_image004.jpg)

This function is a function to modify the content of the template file. There are user-controllable input parameters in line 174, and the content is written to the template file in line 211.

espcms\espcms_admin\control\TemplateFile.php

![img](file:///C:/Users/JeakinsCheung/AppData/Local/Packages/oice_16_974fa576_32c1d314_30a7/AC/Temp/msohtmlclip1/01/clip_image006.jpg)

![img](file:///C:/Users/JeakinsCheung/AppData/Local/Packages/oice_16_974fa576_32c1d314_30a7/AC/Temp/msohtmlclip1/01/clip_image008.jpg)

**Steps to reproduce:**

\1. Log in to the background management page as an administrator

\2. Click Template Management -> Modify and change the content to <?php phpinfo();?>![img](file:///C:/Users/JeakinsCheung/AppData/Local/Packages/oice_16_974fa576_32c1d314_30a7/AC/Temp/msohtmlclip1/01/clip_image010.jpg)

![img](file:///C:/Users/JeakinsCheung/AppData/Local/Packages/oice_16_974fa576_32c1d314_30a7/AC/Temp/msohtmlclip1/01/clip_image012.jpg)

\3. After the modification is successful, save it, and access the home page to cause the code to execute.![img](file:///C:/Users/JeakinsCheung/AppData/Local/Packages/oice_16_974fa576_32c1d314_30a7/AC/Temp/msohtmlclip1/01/clip_image014.jpg)