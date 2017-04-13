---
title: "&lt;add&gt;-Element f&#252;r connectionManagement (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#add"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add>-Element, connectionManagement"
  - "<connectionManagement>, add-Element"
  - "add-Element, connectionManagement"
  - "connectionManagement, add-Element"
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# &lt;add&gt;-Element f&#252;r connectionManagement (Netzwerkeinstellungen)
Fügt der Verbindungsverwaltungsliste eine IP\-Adresse oder einen DNS\-Namen hinzu.  
  
## Syntax  
  
```  
  
        <add   
   address = "address expression"   
   maxconnection = integer   
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Attribut**|**Beschreibung**|  
|------------------|----------------------|  
|`address`|Eine Zeichenfolge, die eine IP\-Adresse oder einen DNS\-Namen beschreibt.|  
|`maxconnection`|Die maximale Anzahl von Verbindungen, die für einen Server zulässig sind.  Wenn keine Angabe erfolgt, wird der Standardwert "2" verwendet.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|**Beschreibung**|  
|-----------------|----------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.|  
  
## Hinweise  
 Der Wert des `address`\-Attributs muss entweder ein Sternchen zur Angabe aller Verbindungen oder eine Zeichenfolge im Format `<schema>://<idn_hostname>[:<port>]` sein.  
  
 Enthält der an HTTP\-APIs übergebene URI Unicode, wird der Name intern mit <xref:System.Uri.DnsSafeHost%2A> umgewandelt, wodurch möglicherweise eine Punycode\-Zeichenfolge zurückgegeben wird \(das Verhalten ist von der aktuellen IDN\-Konfiguration abhängig\).  
  
## Konfigurationsdateien  
 Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei \("Machine.config"\) verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird eine Anwendung für die Verwendung von vier Verbindungen mit dem Server "www.contoso.com" und zwei Verbindungen mit allen anderen Servern konfiguriert.  
  
```  
<configuration>  
  <system.net>  
    <connectionManagement>  
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