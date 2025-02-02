# DockerHandbook

1. Kontainerlarning ro'yxatini ko'rish

       docker container ls
       docker ps
       docker container ls -a  # Barcha ishlab turgan va ishlamayotgan kontainerlarni ko'rish   
   Versiyani ko'rish

       docker version
   Kontainerni ishga tushirish

       docker container run image_name
       docker container run alpine  # alpine imageni ishga tushirish va kontainer hosil qilish
       docker container run -it image_name sh  # imageni kontainer sifatida ishga tushirish va uning terminalini ochish
   Kontainerni to'xtatish

       exit
   Ishlamayotgan containerni ishga tushirish

       docker container start container_name
   
