# Hello World project using Maven
Maven Source Code for Google Code-in.

This is a repository containing the Maven Test App source code that I have created to complete my assignment on Google Code-In. 
My username is binzzz.

### Instructions to make "hello world" project  based on Maven:

#### 1. Download Java JDK and Maven 3.6.3
If you already installed Java JDK, continue to download Maven.
- Download Java JDK using the link below.
https://www.oracle.com/technetwork/java/javase/downloads/index.html
- Extract Java JDK to a specified location. Mine is set to Download.

#### 2. Download Maven
- Go to
> cd /opt/
- Download Maven using the command below.
> sudo wget https://www-us.apache.org/dist/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz
- Then do the following command.
> sudo tar -xf apache-maven-3.6.3-bin.tar.gz
> sudo mv apache-maven-3.5.3/ apache-maven/
> sudo update-alternatives --install /usr/bin/mvn maven /opt/apache-maven/bin/mvn 1001

#### 3. Configuring Maven
- Do the following command.
> cd /etc/profile.d/
> sudo gedit maven.sh
- Add the lines below then save it.
> export JAVA_HOME=/usr/lib/jvm/java-8-oracle
> export M2_HOME=/opt/apache-maven
> export MAVEN_HOME=/opt/apache-maven
> export PATH=${M2_HOME}/bin:${PATH}
- After you save it, do the following command.
> sudo chmod +x maven.sh
> sudo source maven.sh

#### 3. Configuring Java JDK
- Do the following command. According to your editor. I'm using vim as my editor.
> sudo vim /etc/profile
- Then add these 2 lines to the end of the file.
> export JAVA_HOME="/this points out to your java jdk extracted location"  
> export PATH=JAVA_HOME/bin:$PATH
- Then do the following command
> source /etc/environment
- Check if your Maven is installed by using the command
> mvn --version
- If you have succeded you should see a respon like this.
> Apache Maven 3.6.3 (cecedd343002696d0abb50b32b541b8a6ba2883f)
> Maven home: /opt/apache-maven-3.6.3
> Java version: 1.8.0_45, vendor: Oracle Corporation
> Java home: /Library/Java/JavaVirtualMachines/jdk1.8.0_45.jdk/Contents/Home/jre
> Default locale: en_US, platform encoding: UTF-8
> OS name: "mac os x", version: "10.8.5", arch: "x86_64", family: "mac"

#### 4. Creating a "Hello World!" project.
- Do the following command. You may need to repeat it a few times until it shows that your build is succeded. This happens because the remote server may time out before your downloads are complete.
> mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4 -DinteractiveMode=false
- You will notice that the generate goal created a directory with the same name given as the artifactId.
> cd my-app
- Explore around the folder and you will see a couple of important things. Such as the **POM.xml **and **App.java.**
- Once you've done editing those to main files. Go ahead and build the package using the following command.
> mvn package
- You should see the success message if you're doing it right. Next you may test the newly compiled and packaged JAR with the following command:
> java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App


