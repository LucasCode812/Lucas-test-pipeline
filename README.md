### CI/CD Pipeline for Main Branch Deployment
#Dit is een CI/CD-pijplijn die is opgezet voor het implementeren van code van de main branch in de test en prod omgevingen.

# De pijplijn bestaat uit twee jobs, deploy-test en deploy-prod. De deploy-test job wordt geactiveerd door push-events op de main branch. Het draait op een Ubuntu-machine en de testomgeving wordt gedefinieerd met de environment sleutel.

# In de deploy-test job wordt de code gecontroleerd op fouten en worden de test-server en de firewall in de onderhoudsmodus gezet. De code wordt vervolgens naar de test-server gedeployed en de firewall wordt weer geopend om de test-server toegankelijk te maken. Tenslotte wordt de toegankelijkheid van de test-server getest.

# De deploy-prod job is afhankelijk van de deploy-test job en wordt pas uitgevoerd nadat de testen in orde zijn bevonden en nadat een handmatige goedkeuring is gegeven door de opgegeven approver. Het doel van deze job is om de code van de main branch te implementeren op de productie-server.

# De deploy-prod job wordt uitgevoerd op een Ubuntu-machine en de productieomgeving wordt gedefinieerd met de environment sleutel. De stappen in de deploy-prod job zijn vergelijkbaar met die van de deploy-test job, met als enige verschil dat de productie-server in de onderhoudsmodus wordt gezet voordat de code wordt gedeployed. Tenslotte wordt de toegankelijkheid van de productie-server getest.
