---
title: "&lt;client&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#client"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# &lt;client&gt;
Das `client`\-Element definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.  
  
## Syntax  
  
```  
  
<system.serviceModel>  
    <client>  
        <endpoint>  
        </endpoint>  
                <metadata>  
        </metadata>  
    </client>  
</system.serviceModel>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Endpunkt \(endpoint\)\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|Enthält eine Auflistung der Endpunktelemente, die die Endpunkte angeben, mit denen dieser Client eine Verbindung herstellen kann.|  
|[\<Metadaten\>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|Enthält Einstellungen zum Verarbeiten von Metadaten.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|Das Stammelement aller Windows Communication Foundation \(WCF\)\-Konfigurationselemente.|  
  
## Hinweise  
 Der `client`\-Abschnitt definiert eine Liste der Endpunkte, mit denen ein Client eine Verbindung herstellen kann.  Jeder im Clientabschnitt aufgeführte Endpunkt definiert seine eigene Bindung, sein eigenes Verhalten und seinen eigenen Vertrag.  Er wird eindeutig anhand der Kombination des `name`\-Attributs mit dem `contract`\-Attribut identifiziert.  Der Clientcode gibt den `name` an, um eine Verbindung zu einem Endpunkt für den durch den Client implementierten Dienst herzustellen.  Wenn das `name`\-Attribut ausgelassen wird, fungiert der Endpunkt als Standardendpunkt für den Vertrag, den er implementiert.  
  
 Darüber hinaus gibt dieser Abschnitt auch die Einstellungen zum Verarbeiten von Metadaten an.  
  
## Beispiel  
  
```  
<client>  
    <endpoint address="/HelloWorld/"  
              bindingConfiguration="usingDefaults"  
              name="MyBinding"  
              binding="customBinding"  
              contract="HelloWorld">  
    <addressProperties actingAs="http://www.microsoft.com/TestActor"  
             identityData="BasicReadWrite" identityType="Spn" isAddressPrivate="false">  
    </endpoint>  
</client>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.ClientSection>   
 <xref:System.ServiceModel.Configuration.MetadataElement>   
 [WCF\-Clientkonfiguration](../../../../../docs/framework/wcf/feature-details/client-configuration.md)   
 [Clients](../../../../../docs/framework/wcf/feature-details/clients.md)