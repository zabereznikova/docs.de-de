---
title: "&lt;allowAccounts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;allowAccounts&gt;
Enthält eine Auflistung von Konfigurationselementen, die Benutzerkonten für Prozesse angeben, die [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.  
  
 \<system.serviceModel.activation\>  
  
## Syntax  
  
```  
  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|Fügt ein Benutzerkonto für Prozesse hinzu, die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]\-Dienste hosten und Verbindungszugriff auf den Freigabedienst haben.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<net.pipe\>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) oder [\<net.tcp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)|Gibt die Konfigurationseinstellungen für den Freigabedienst Net Pipe oder TCP an.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>   
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>   
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>   
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>