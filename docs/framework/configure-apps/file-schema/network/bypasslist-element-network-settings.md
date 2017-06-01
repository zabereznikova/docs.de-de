---
title: "&lt;bypasslist&gt;-Element (Netzwerkeinstellungen) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<bypasslist>-Element"
  - "bypasslist-Element"
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
caps.latest.revision: 17
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 17
---
# &lt;bypasslist&gt;-Element (Netzwerkeinstellungen)
Stellt eine Reihe von regulären Ausdrücken bereit, die Adressen beschreiben, die keinen Proxy verwenden.  
  
## Syntax  
  
```  
  
      <bypasslist>   
</bypasslist>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine.  
  
### Untergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|Fügt der Proxyumgehungsliste eine IP\-Adresse oder einen DNS\-Namen hinzu.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|Bereinigt die Umgehungsliste.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|Entfernt die IP\-Adresse oder den DNS\-Namen aus der Proxyumgehungsliste.|  
  
### Übergeordnete Elemente  
  
|**Element**|****Beschreibung****|  
|-----------------|--------------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Konfiguriert den HTTP\-Proxyserver \(Hypertext Transfer Protocol\).|  
  
## Hinweise  
 Die Umgehungsliste enthält reguläre Ausdrücke, die URIs beschreiben, auf die <xref:System.Net.WebRequest>\-Instanzen nicht über den Proxyserver, sondern direkt zugreifen.  
  
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