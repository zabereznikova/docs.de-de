---
title: "Erstellen von Internetanforderungen | Microsoft Docs"
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
  - "WebRequest-Klasse, Senden und Empfangen von Daten"
  - "Netzwerk"
  - "HttpWebResponse-Klasse, Senden und Empfangen von Daten"
  - "Anfordern von Daten aus dem Internet, Erstellen von Anforderungen"
  - "Netzwerkressourcen"
  - "Internet, Anfordern von Daten"
  - "Datenanforderungen, Erstellen von Anforderungen"
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Erstellen von Internetanforderungen
Anwendungen erstellen <xref:System.Net.WebRequest>\-Instanzen durch die <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName>\-Methode.  Dies ist eine statische Methode, die eine Klasse erstellt, die von **WebRequest** auf dem URI\-Schema berechnet wird, das an ihne übergeben wird.  
  
## Internet, Datei\- und FTP\-Anforderungen  
 . .NET Framework stellt die <xref:System.Net.HttpWebRequest>\-Klasse, die von **WebRequest** abgeleitet ist, dass HTTP und HTTPS\-Anforderungen zu bearbeiten.  In den meisten Fällen stellt die **WebRequest**\-Klasse alle Eigenschaften, die Sie einen Anwendung um müssen; jedoch ggf., können Sie **WebRequest**\-Objekte umwandeln, die durch die **WebRequest.Create**\-Methode zum **HttpWebRequest**\-Typ erstellt werden, um auf die HTTP\-spezifische Eigenschaften der Anforderung zuzugreifen.  Entsprechend die **HttpWebResponse**\-Objekthandles die Antworten von HTTP und HTTPS\-Anforderungen.  Um auf die HTTP\-spezifische Eigenschaften **HttpWebResponse** wenden Sie zuzugreifen, müssen Sie **WebResponse**\-Objekte in den Typ umwandeln **HttpWebResponse**  ein.  
  
 . .NET Framework stellt auch die <xref:System.Net.FileWebRequest> und <xref:System.Net.FileWebResponse> für Klassen Clientanforderungen für Ressourcen bereit, die die "Datei verwenden: " URI\-Schema.  Entsprechend werden <xref:System.Net.FtpWebRequest> und die <xref:System.Net.FtpWebResponse> für Klassen Clientanforderungen für Ressourcen bereitgestellt, die das "FTP verwenden: " Schema.  Wenn die Anforderung für eine Ressource ist, die alle Schemas verwendet, können Sie die **WebRequest.Create**\-Methode verwenden, um ein Objekt abzurufen, mit dem die Anwendung um.  
  
 Um Anforderungen zu behandeln die andere Protokolle auf Anwendungsebene verwenden, müssen Sie die protokollspezifischen Klassen implementieren, die von **WebRequest**  und von  **WebResponse** abgeleitet werden.  Weitere Informationen finden Sie unter [Programmieren von austauschbare Protokolle](../../../docs/framework/network-programming/programming-pluggable-protocols.md).  
  
## Siehe auch  
 [Gewusst wie: Anfordern von Daten mithilfe der WebRequest\-Klasse](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)   
 [Anfordern von Daten](../../../docs/framework/network-programming/requesting-data.md)