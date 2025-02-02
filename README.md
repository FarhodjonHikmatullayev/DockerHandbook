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
       docker container run --rm -it --name=new_name image_name sh  # docker containerga nom berib uni run qilish
       docker container run -it image_name sh  # imageni kontainer sifatida ishga tushirish va uning terminalini ochish
       docker container run -itd iamge_name sh  # imageni container sifatida ishga tushiradi va uning terminalini ochmaydi ya'ni ichiga kirmaydi
       docker container run --rm -it alpine sh  # container ishini tugatgach o'chib ketadi

       ctrl + P + Q  # containerni o'chirmagan holatda chiqib ketish
   Kontainerni to'xtatish

       exit  # container ichida
   Ishlamayotgan containerni ishga tushirish

       docker container start container_name
   Kontainerga ulanish

       docker container attach container_name
   Kontainerni to'xtatish

       docker container stop container_name
       docker container kill container_name  # darxol to'xtatish
       docker container rm container_name  # o'chirib yuborish
       docker container prune  # barcha to'xtab turgan containerlarni o'chirib tashlash
   Kontainerning tashqarisida turib kontainer ichiga buyruq berish

       docker container exec container_name command_name
       docker container exec my_container ls  # docker ichida ls ni ishlatib uning tashqarisida natijani ko'rish
     
   
