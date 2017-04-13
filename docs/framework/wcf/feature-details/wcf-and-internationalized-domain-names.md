---
title: "WCF und internationale Dom&#228;nennamen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c8a3e10a-8bc2-4a78-8d86-a562ba6e65fa
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# WCF und internationale Dom&#228;nennamen
Unterstützung für WCF\-Dienste mit internationalisierten Domänennamen \(Internationalized Domain Names, IDNs\) wurde hinzugefügt.  Ein internationalisierter Domänenname ist ein Domänenname, der Nicht\-ASCII\-Zeichen enthält.  Diese Unterstützung umfasst die Fähigkeit zum Hosten eines WCF\-Diensts mit einem IDN und zum Kommunizieren eines WCF\-Clients mit einem Webdienst, der über einen IDN verfügt.  
  
## System.Uri und IDN  
 <xref:System.Uri> verfügt über die beiden Eigenschaften <xref:System.Uri.Host%2A> und <xref:System.Uri.DnsSafeHost%2A>.  Diese Eigenschaften enthalten abhängig von den IDN\-Konfigurationseinstellungen Unicode\- oder Punycode\-Werte.  
  
 IDN wird in der Konfigurationsdatei einer Anwendung mit dem folgenden XML\-Code aktiviert:  
  
```  
<configuration>  
  <uri>  
    <idn enabled="All/AllExceptIntranet/None" />  
  </uri>  
</configuration>  
  
```  
  
 Das \<idn\>\-Element enthält das aktivierte Attribut, das auf einen der folgenden Werte festgelegt werden kann:  
  
1.  "None"  
  
2.  "AllExceptIntranet"  
  
3.  "All"  
  
 Wenn die IDN\-Einstellung auf "None" festgelegt ist, werden von "Uri.Host" oder "Uri.DnsSafeHost" keine Konvertierungen ausgeführt.  Wenn die IDN\-Einstellung auf "All" festgelegt ist, bleibt für "uri\-Host" Unicode festgelegt, und "uri.DnsSafeHost" wird in Punycode konvertiert.  Wenn die IDN\-Einstellung auf "AllExceptIntranet" festgelegt ist, wird "uri.DnsSafeHost" für Internetadressen in Punycode konvertiert, und bei Intranetadressen wird Unicode beibehalten.  Diese Einstellung ist für eine ordnungsgemäße DNS\-Namensauflösung wichtig.  Beachten Sie, dass diese Einstellung für Windows 8 und spätere Versionen nicht konfiguriert werden muss.  
  
> [!WARNING]
>  Sie sollten eine Adresse nie mit Punycode hartcodieren.  WCF konvertiert sie auf Grundlage der verwendeten Konfigurationseinstellungen.  
  
> [!WARNING]
>  Wenn Sie "applicationHost.exe.config" Unicode\-Zeichen hinzufügen, speichern Sie die Datei mit UTF\-8\-Codierung.  
  
## Siehe auch  
 [System.Uri](http://msdn.microsoft.com/library/system.uri.aspx)