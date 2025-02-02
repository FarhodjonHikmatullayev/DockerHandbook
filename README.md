# DockerHandbook

1. Kontainerlar asosiy kommandalari

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

2. Docker imagelar uchun asosiy komandalar
   Docker imagelar ro'yxatini ko'rish

       docker image ls
   Docker imageni yuklab olish

       docker image pull image_name::tag_name
       docker image pull hello-world::latest  # for example
   Docker imageni local repositorydan o'chirish

       docker image rm image_name_or_image_id::tag_name  # agar tag_name berilmasa latest tagini defoult oladi
       docker image rm -f image_name_or_image_id::tag_name
       docker image prune  # barcha ishlamayotgan imagelarni o'chirib yuborish
   Docker imagelarning kompyuter xotirasidan egallayotgan joyini ko'rish

       docker system df
   Docker image qurish

       docker image build -t image_name:image_verion file_path
       docker image build -t mynginx:v1.0 .  # Example sifatida shu pathda joylashgan my_nginx image foydalanildi
   Docker file Example - https://youtu.be/qHTs15-_mdU?si=v610_4m6WmtsXt_K

       FROM debian:buster-slim
       RUN apt-get update    # bir RUN ichida bir nechta buyruqlarni yozish uchun && dan foydalaniladi
       RUN apt-get install -y nginx
       COPY ./nginx1.html /var/www/html
       CMD nginx -g 'daemon off;'
   Docker containerdagi portni local containerdagi portga bog'lash

       docker container run -p local_port:container_port
       docker container run -p 80:80  # example
       docker container run -d -p 80:80 nginx
       docker container run -d -p 127.0.0.1:80:80 nginx  # ip manzilini ham qo'shish
       docker container run -d -p 83:80 -p 444:443 nginx  # har bir portni alohida mapping qilish
       docker container run -d -p 5000-5200:5000-5200 nginx  # 5000 portdan boshlab 5200 portgacha mapping qilish
   Local kompyuterdagi barcha IP manzillarni ko'rish

       ipconfig  # cmd oynasida beriladi
   Containerni sinab ko'rish

       docker container run -d -p 6379:6379 redis
       telnet localhost 6379  # redis containerga ulannish  ping-pong
3. Docker Hubga local imagelarni yuklash

       docker image ls  # localdagi imagelar ro'yxatini ko'rish
   Login qilish

       docker login -u username
       docker image tag image_name:tag_name repo_name
       docker image tag redis:latest farhodhikmatullayev/myredis:6.0.7  # for example
       docker image push farhodhikmatullayev/myredis:6.0.7  # push qilish
   
   
     
   
