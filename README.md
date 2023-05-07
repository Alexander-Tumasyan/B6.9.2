# Задание B6.9.2

1. Создайте Ansible-роль, настраивающую кэширующий DNS-сервер dnsmasq. Примените ее.  

    **Запустить плейбук: ansible-playbook dnsmasq.yaml --ask-become**  

2. Напишите Ansible-playbook, создающий группу пользователей superusers, куда входят пользователи user2 и user3, и которая, выполнив sudo -i, сможет повысить свои полномочия и стать root-пользователем. Можете использовать модуль lineinfile. У него есть параметр validate, позволяющий проверять сделанные изменения в файле. В документации есть пример валидации sudoers-файла.  

    **Запустить плейбук: ansible-playbook superusers.yaml --ask-become**  

    [Документация по модулю lineinfile](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/lineinfile_module.html)

3.     Самостоятельно напишите Ansible-роль, настраивающую связку nginx+php-fpm и выдающую при обращении к главной странице веб-сервера информацию о php (содержимое index.php — <?php phpinfo();?>).

    **Запустить плейбук: ansible-playbook nginx_phpfpm.yaml --ask-become**  

4. Дополните роль из п.3: пусть DocumentRoot будет в директории /opt/nginx/ansible. Используйте handler для перечитывания конфигурации nginx.  

    **Блоки в task/main.yml**  

    - **name: Create a directory if it does not exist**
    - **name: Copy DocumentRoot with owner and permissions**
    - **name: Replace a root path in sites-avalaible**
