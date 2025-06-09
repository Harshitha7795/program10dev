 name: Deploy artifact built by Jenkins
  hosts: localhost
  become: yes
  tasks:
    - name: Create deployment directory if not exists
      file:
        path: /opt/deploy
        state: directory
        mode: '0755'

    - name: Copy JAR to deployment folder
      copy:
        src: /mnt/c/Users/laksh/m8/target/m8-1.0-SNAPSHOT.jar
        dest: /opt/deploy/m8-1.0-SNAPSHOT.jar
        mode: '0644'
