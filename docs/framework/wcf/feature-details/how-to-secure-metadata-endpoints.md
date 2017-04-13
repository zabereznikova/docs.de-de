---
title: "Gewusst wie: Sichere Metadatenendpunkte | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9f71b6ae-737c-4382-8d89-0a7b1c7e182b
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# Gewusst wie: Sichere Metadatenendpunkte
Metadaten für einen Dienst können vertrauliche Informationen über Ihre Anwendung enthalten, die böswillige Benutzer für ihre Zwecke missbrauchen können.Die Consumer Ihres Diensts benötigen möglicherweise auch einen sicheren Mechanismus für den Zugriff auf Metadaten über Ihren Dienst.Deshalb ist es manchmal notwendig, die Metadaten mit einem sicheren Endpunkt zu veröffentlichen.  
  
 Metadatenendpunkte sind in der Regel mit den Standardsicherheitsmechanismen, die in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zum Sichern von Anwendungsendpunkten definiert werden, gesichert.\([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md).\)  
  
 In diesem Thema sind die Schritte zur Erstellung eines Endpunkts beschrieben, der durch ein Verbunddienst\-SSL\-Zertifikat gesichert ist, also anders ausgedrückt: die Schritte zur Erstellung eines HTTPS\-Endpunkts.  
  
### So erstellen Sie einen sicheren HTTPS\-GET\-Metadatenendpunkt in Code  
  
1.  Konfigurieren Sie einen Anschluss mit einem entsprechenden X.509\-Zertifikat.Das Zertifikat muss von einer vertrauenswürdigen Stelle stammen und für die Verwendung zum Zwecke der Dienstautorisierung beabsichtigt sein. Sie müssen das Tool HttpCfg.exe verwenden, um das Zertifikat an den Anschluss anzufügen.Informationen finden Sie unter [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL\-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
    > [!IMPORTANT]
    >  Der Betreff des Zertifikats oder das DNS \(Domain Name System\) muss mit dem Namen des Computers übereinstimmen.Dies ist deshalb wichtig, weil einer der ersten Schritte des HTTPS\-Mechanismus darin besteht, zu überprüfen, ob das Zertifikat für denselben URI \(Uniform Resource Identifier\) ausgestellt wurde wie die Adresse, von der aus es aufgerufen wird.  
  
2.  Erstellen Sie eine neue Instanz der <xref:System.ServiceModel.Description.ServiceMetadataBehavior>\-Klasse.  
  
3.  Legen Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>\-Eigenschaft der <xref:System.ServiceModel.Description.ServiceMetadataBehavior>\-Klasse auf `true` fest.  
  
4.  Legen Sie für die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>\-Eigenschaft einen geeigneten URL fest.Beachten Sie, dass die URL mit dem Schema "https:\/\/" beginnen muss, wenn Sie eine absolute Adresse angeben.Wenn Sie eine relative Adresse angeben, müssen Sie eine HTTPS\-Basisadresse für den Diensthost angeben.Wenn diese Eigenschaft nicht festgelegt ist, lautet die Standardadresse "" oder befindet sich direkt an der HTTPS\-Basisadresse für den Dienst.  
  
5.  Fügen Sie der Verhaltenssammlung die Instanz hinzu, die von der <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>\-Eigenschaft der <xref:System.ServiceModel.Description.ServiceDescription>\-Klasse zurückgegeben wird, wie im folgenden Code dargestellt.  
  
     [!code-csharp[c_HowToSecureEndpoint#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#1)]
     [!code-vb[c_HowToSecureEndpoint#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#1)]  
  
### So erstellen Sie einen sicheren HTTPS\-GET\-Metadatenendpunkt in der Konfiguration  
  
1.  Fügen Sie dem [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)\-Element der Konfigurationsdatei für Ihren Dienst ein [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)\-Element hinzu.  
  
2.  Fügen Sie dem [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)\-Element ein [\<serviceBehaviors\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)\-Element hinzu.  
  
3.  Fügen Sie dem `<serviceBehaviors>`\-Element ein [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)\-Element hinzu.  
  
4.  Legen Sie einen angemessenen Wert für das `name`\-Attribut des `<behavior>`\-Elements fest.Das `name`\-Attribut ist erforderlich.Das nachstehende Beispiel verwendet den Wert `mySvcBehavior`.  
  
5.  Fügen Sie dem `<behavior>`\-Element ein [\<serviceMetadata\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)\-Element hinzu.  
  
6.  Legen Sie das `httpsGetEnabled`\-Attribut des `<serviceMetadata>`\-Elements auf `true` fest.  
  
7.  Legen Sie einen angemessenen Wert für das `httpsGetUrl`\-Attribut des `<serviceMetadata>`\-Elements fest.Beachten Sie, dass die URL mit dem Schema "https:\/\/" beginnen muss, wenn Sie eine absolute Adresse angeben.Wenn Sie eine relative Adresse angeben, müssen Sie eine HTTPS\-Basisadresse für den Diensthost angeben.Wenn diese Eigenschaft nicht festgelegt ist, lautet die Standardadresse "" oder befindet sich direkt an der HTTPS\-Basisadresse für den Dienst.  
  
8.  Um das Verhalten mit einem Dienst zu suchen, legen Sie für das `behaviorConfiguration`\-Attribut des [\<service\>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md)\-Elements denselben Wert fest wie für das Namensattribut des Verhaltenselements.Der folgende Konfigurationscode zeigt ein vollständiges Beispiel.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="mySvcBehavior">  
         <serviceMetadata httpsGetEnabled="true"   
              httpsGetUrl="https://localhost:8036/calcMetadata" />  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
     <services>  
      <service behaviorConfiguration="mySvcBehavior"   
            name="Microsoft.Security.Samples.Calculator">  
       <endpoint address="http://localhost:8037/ServiceModelSamples/calculator"  
       binding="wsHttpBinding" bindingConfiguration=""     
       contract="Microsoft.Security.Samples.ICalculator" />  
      </service>  
     </services>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
## Beispiel  
 Im folgenden Beispiel wird eine Instanz einer <xref:System.ServiceModel.ServiceHost>\-Klasse erstellt und ein Endpunkt hinzugefügt.Anschließend erstellt der Code eine Instanz der <xref:System.ServiceModel.Description.ServiceMetadataBehavior>\-Klasse und legt die Eigenschaften zur Erstellung eines sicheren Punkts für den Metadatenaustausch fest.  
  
 [!code-csharp[c_HowToSecureEndpoint#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#0)]
 [!code-vb[c_HowToSecureEndpoint#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#0)]  
  
## Kompilieren des Codes  
 Das Codebeispiel verwendet die folgenden Namespaces:  
  
-   <xref:System.ServiceModel?displayProperty=fullName>  
  
-   <xref:System.ServiceModel.Description?displayProperty=fullName>  
  
## Siehe auch  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>   
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>   
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>   
 [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL\-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)   
 [Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Sicherheitsüberlegungen für Metadaten](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)   
 [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)