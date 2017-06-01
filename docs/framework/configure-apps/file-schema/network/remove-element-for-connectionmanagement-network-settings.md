---
title: "&lt;Remove&gt;-Element f&#252;r connectionManagement (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<connectionManagement>, remove-Element"
  - "<remove>-Element, connectionManagement"
  - "connectionManagement, remove-Element"
  - "remove-Element, connectionManagement"
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# &lt;Remove&gt;-Element f&#252;r connectionManagement (Netzwerkeinstellungen)
Entfernt die IP\-Adresse oder den DNS\-Namen aus der Verbindungsverwaltungsliste.  
  
## Syntax  
  
```  
  
      <remove   
   name = "server name or IP address"   
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Attribute**|****Beschreibung****|  
|-------------------|--------------------------|  
|`address`|Eine IP\-Adresse oder ein DNS\-Name.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Gibt die maximale Anzahl von Verbindungen zu einem Netzwerkhost an.|  
  
## Hinweise  
 Das `remove`\-Element entfernt den Verbindungsverwaltungslisten\-Eintrag für den angegebenen Server.  
  
 Der Wert des `address`\-Attributs sollte eine gültige IP\-Adresse oder ein gültiger Hostname sein.  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Das folgende Beispiel entfernt alle Verbindungsverwaltungslisten\-Einträge für den Server www.adventure\-works.com und konfiguriert anschließend eine Anwendung so, dass vier Verbindungen zum Server www.contoso.com und zwei Verbindungen zu allen anderen Servern verwendet werden.  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address = "http://www.adventure-works.com"/>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.ServicePoint>   
 <xref:System.Net.ServicePointManager>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)