---
title: "HttpListener | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "HTTP"
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# HttpListener
Die <xref:System.Net.HttpListener>\-Klasse stellt einen programmgesteuerten HTTP\-Protokolllistener bereit.  Der Listener ist für die Lebensdauer des <xref:System.Net.HttpListener>\-Objekts aktiv und wird in der Anwendung ausgeführt.  
  
## HTTP.SYS  
 Die <xref:System.Net.HttpListener>\-Klasse basiert auf HTTP.sys; hierbei handelt es sich um den Kernelmoduslistener, der den gesamten HTTP\-Verkehr für Windows verarbeitet.  HTTP.sys bietet Verbindungsverwaltung, Bandbreiteneinschränkung und Webserverprotokollierung.  Verwenden Sie das Tool "`HttpCfg.exe`", um SSL\-Zertifikate hinzuzufügen.  Weitere Informationen finden Sie in der Dokumentation zum Tool [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) in der [Server](http://go.microsoft.com/fwlink/?LinkID=178285)\-Dokumentation.  
  
## Siehe auch  
 <xref:System.Net.HttpListener>   
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.HttpWebResponse>   
 [HTTP\-Server](http://go.microsoft.com/fwlink/?LinkID=178285)   
 [Sicherheitsverbesserungen für Internetinformationen](http://go.microsoft.com/fwlink/?LinkID=178286)   
 [HttpListener\-ASPX\-Hostanwendungsbeispiel](http://go.microsoft.com/fwlink/?LinkID=179560)   
 [HttpListener\-Technologiebeispiel](http://go.microsoft.com/fwlink/?LinkID=179558)   
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)