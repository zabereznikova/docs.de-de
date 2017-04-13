---
title: "&lt;remove&gt;-Element f&#252;r bypasslist (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#remove"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<bypasslist>, remove-Element"
  - "bypasslist, remove-Element"
  - "remove-Element, bypasslist"
  - "remove-Element, bypasslist"
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 16
---
# &lt;remove&gt;-Element f&#252;r bypasslist (Netzwerkeinstellungen)
Entfernt die IP\-Adresse oder den DNS\-Namen aus der Proxyumgehungsliste.  
  
## Syntax  
  
```  
  
      <remove   
   name = "regular expression"   
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Attribute**|****Beschreibung****|  
|-------------------|--------------------------|  
|`name`|Ein regulärer Ausdruck, der eine IP\-Adresse oder einen DNS\-Namen beschreibt.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.|  
  
## Hinweise  
 Das `remove`\-Element entfernt reguläre Ausdrücke, die IP\-Adressen oder DNS\-Servernamen beschreiben, aus der Liste der Adressen, die einen Proxyserver umgehen.  Diese Adressen wurden weiter oben in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationshierarchie definiert.  
  
 Der Wert für das `name`\-Attribut sollte ein regulärer Ausdruck sein, der eine Gruppe von IP\-Adressen oder Hostnamen beschreibt.  
  
 Weitere Informationen zu regulären Ausdrücken finden Sie unter [Reguläre Ausdrücke von .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Im folgenden Codebeispiel wird jegliche frühere Definition für die adventure\-works.com\-Domäne entfernt und dann die contoso.com\-Domäne zur Umgehungsliste hinzugefügt.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <remove name = "[a-z]+\.adventure-works\.com$" />  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)