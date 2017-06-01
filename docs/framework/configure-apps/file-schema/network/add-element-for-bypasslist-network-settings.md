---
title: "&lt;add&gt;-Element f&#252;r bypasslist (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#add"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<add>-Element, bypasslist"
  - "<bypasslist>, add-Element"
  - "add-Element, bypasslist"
  - "bypasslist, add-Element"
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# &lt;add&gt;-Element f&#252;r bypasslist (Netzwerkeinstellungen)
Fügt der Proxyumgehungsliste eine IP\-Adresse oder einen DNS\-Namen hinzu.  
  
## Syntax  
  
```  
  
      <add   
   address = "regular expression"   
/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|**Attribute**|****Beschreibung****|  
|-------------------|--------------------------|  
|**address**|Ein regulärer Ausdruck, der eine IP\-Adresse oder einen DNS\-Namen beschreibt.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.|  
  
## Hinweise  
 Das `add`\-Element fügt der Liste der Adressen, die einen Proxyserver umgehen, reguläre Ausdrücke hinzu, die IP\-Adressen oder DNS\-Servernamen beschreiben.  
  
 Der Wert des `address`\-Attributs sollte ein regulärer Ausdruck sein, der eine Gruppe von IP\-Adressen oder Hostnamen beschreibt.  
  
 Lassen Sie beim Angeben eines regulären Ausdrucks für dieses Element Vorsicht walten.  Der reguläre Ausdruck "\[a\-z\]\+\\.contoso\\.com" entspricht jedem Host in der contoso.com\-Domäne und auch in der contoso.com.cpandl.com\-Domäne.  Verwenden Sie einen Anker \("$"\), damit der Ausdruck nur mit einem Host in der contoso.com\-Domäne übereinstimmt: "\[a\-z\]\+\\.contoso\\.com$".  
  
 Weitere Informationen zu regulären Ausdrücken finden Sie unter [Reguläre Ausdrücke von .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## Konfigurationsdateien  
 Dieses Element kann in der Konfigurationsdatei der Anwendung oder in der Konfigurationsdatei des Computers \(Machine.config\) verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel werden der Umgehungsliste zwei Adressen hinzugefügt.  Im ersten Beispiel wird der Proxy für alle Server in der **contoso.com**\-Domäne umgangen. Im zweiten Beispiel wird der Proxy für alle Server umgangen, deren IP\-Adressen mit 192.168 beginnen.  
  
```  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.Net.WebProxy?displayProperty=fullName>   
 [Netzwerkeinstellungsschema](../../../../../docs/framework/configure-apps/file-schema/network/index.md)