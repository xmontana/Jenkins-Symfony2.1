Jenkins Symfony2.1
=========================

Based on alex88' Symfony 2.1. template: https://github.com/alex88/symfony2.1-jenkins-template and sebastianbergmann' PHP-jenkins-template https://github.com/sebastianbergmann/PHP-jenkins-template .


### Install Jenkins and PHP-TEMPLATE

First, follow the instructions from http://jenkins-php.org/ for installing Jenkins.

On Ubuntu, you can install with 

     apt-get install jenkins

Remember to intall PEAR phpunit	and phpDox. Obviously, install configure PHP to run Symfony checking app/check.php.

Process to install the template:

1. Download and install the job template 

     cd $JENKINS_HOME/jobs  
     mkdir php-template  
     cd php-template  
     wget https://github.com/xmontana/php-jenkins-template/raw/master/php-jenkins-template/config.xml  
     cd ..  
     chown -R jenkins:jenkins php-template/

2. Reload Jenkins' configuration.

3. Click on "New Job".

4. Enter a "Job name".

5. Select "Copy existing job" and enter "php-template" into the "Copy from" field.

6. Click "OK".

7. Disable the "Disable Build" option.

8. Fill in your "Source Code Management" information.

9. Configure a "Build Trigger", for instance "Poll SCM".

10. Click "Save".     

If you have any problems, please check http://jenkins-php.org/


### Configuring Symfony2.1 Project


1. Clone this repository:
    git clone git@github.com:xmontana/php-jenkins-template.git/jenking-symfony2.1

2. Move the "jenkins" folder insde folder "jenking-symfony2.1" to `[SYMFONY2_ROOT]/app/Resources/` inside your Symfony2 project.

3. Move `build.xml` to the root folder of your Symfony2 application.

4. Move `phpunit.xml` to `[SYMFONY2_ROOT]/app` folder or update the existing one. The `logging` node is needed!

5. Add th [symfony2-coding-standards](https://github.com/opensky/Symfony2-coding-standard) in your phpcs naming it as `Symfony2` or edit the phpcs target on build.xml with the right parameters for your envirement.

You can customize the configuration as you want, this works fine with me :)

Note: This template is for Symfony2.1 with composer.

Note2: The build procedure will copy parameters.yml.dist to parameters.yml remember that you don't commit this file for best practices.