nodo {
  etapa ( 'SCM' ) {
    scm de pago
  }
  stage( 'Análisis de SonarQube' ) {
     def scannerHome = herramienta 'SonarScanner' ;
    conSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
