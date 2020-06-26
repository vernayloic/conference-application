## Conference App

TP:  
1- Integrer ce repo dans jenkins   
2- Tester chaque etape  
3- Deployer cette application sur le VM Centos -Remote   
    sur cette VM installer Docker avec ansible  
    et deployer l'application avec ansible et AWX   
   le pipeline sera :     
      * maven  
      * sonar  
      * awx  
      * docker-build  
      * docker-run  avec le port 10100  
      * jmeter  
      * selenium  
      * nexus  
4- lancer des tests Jmeter et selenium   
5- creer les fichiers Jenkinsfile et parserules pour parser les erreurs  
6- terminer par sauvegarder le fichier war dans nexus  


