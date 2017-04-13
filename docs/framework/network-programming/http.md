---
title: "HTTP | Microsoft Docs"
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
  - "Protokolle, HTTP"
  - "Senden von Daten, HTTP"
  - "HttpWebResponse-Klasse, Senden und Empfangen von Daten"
  - "HTTP"
  - "Empfangen von Daten, HTTP"
  - "Anwendungsprotokolle, HTTP"
  - "Internet, HTTP"
  - "Netzwerkressourcen, HTTP"
  - "HTTP, Informationen zu HTTP"
  - "HttpWebRequest-Klasse, Senden und Empfangen von Daten"
ms.assetid: 985fe5d8-eb71-4024-b361-41fbdc1618d8
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# HTTP
. .NET Framework stellt umfassende Unterstützung für das HTTP\-Protokoll, das den Großteil aller Internetverkehrs, mit den <xref:System.Net.HttpWebRequest> und <xref:System.Net.HttpWebResponse>\-Klassen bildet.  Diese Klassen, von abgeleitete <xref:System.Net.WebRequest> und von <xref:System.Net.WebResponse>, werden standardmäßig zurückgegeben, wenn die statische <xref:System.Net.WebRequest.Create%2A?displayProperty=fullName>\-Methode einen URI\-Anfang mit "http" oder "https" auftritt.  In den meisten Fällen stellen **WebRequest** und die **WebResponse**\-Klassen alles, dass erforderlich ist, um die Anwendung zu stellen, aber, wenn Sie Zugriff auf HTTP\-spezifische Funktionen benötigen, die als Eigenschaften verfügbar gemacht werden, können Sie diese verwendete Klassen zu **HttpWebRequest** oder zu **HttpWebResponse**.  
  
 **HttpWebRequest** und **HttpWebResponse** kapseln eine standardmäßige HTTP Anforderung\-undAntwort Transaktion und ermöglichen den Zugriff auf allgemeine HTTP\-Headern.  Diese Klassen unterstützen auch die meisten HTTP 1.1\-Funktionen, einschließlich des Pipelines und senden und empfangen Daten in Blöcken, in der Authentifizierung, im preauthentication, in der Verschlüsselung, in der Proxyunterstützung, in der Serverzertifikatsvalidierung und in der Verbindungsverwaltung.  Auf benutzerdefinierte Headerdatei und der Header, die nicht von Eigenschaften bereitgestellt werden, können in gespeichert und von der **Headers**\-Eigenschaft zugegriffen werden.  
  
 **HttpWebRequest** ist die Standardklasse, die von **WebRequest** verwendet wird und muss nicht registriert werden, bevor Sie ein URI zur **WebRequest.Create**\-Methode übergeben können.  
  
 Sie können die Anwendung um, HTTP\-Umleitungen aus dem Festlegen der <xref:System.Net.HttpWebRequest.AllowAutoRedirect%2A>\-Eigenschaft auf **true** \(Standard\) automatisch folgen.  Die Anwendung leitet Anforderungen um, und die [ResponseURI](frlrfsystemnethttpwebresponseclassresponseuritopic)\-Eigenschaft von **HttpWebResponse** enthält die tatsächliche Webressource, die auf die Anforderung reagiert hat.  Wenn Sie die **AllowAutoRedirect** zu **false**, die Anwendung in der Lage sein müssen, Umleitungen als HTTP\-Protokollfehler zu behandeln.  
  
 Anwendungen empfangen HTTP\-Protokollfehler, indem sie <xref:System.Net.WebException> mit <xref:System.Net.WebException.Status%2A> abfangen, das zu [WebExceptionStatus.ProtocolError](frlrfsystemnetwebexceptionstatusclasstopic) festgelegt ist.  Die <xref:System.Net.WebException.Response%2A>\-Eigenschaft enthält **WebResponse**, das durch den Server gesendet wird und gibt den eigentlichen auftretenden HTTP\-Fehler an.  
  
## Siehe auch  
 [Zugreifen auf das Internet über einen Proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)   
 [Gewusst wie: Zugreifen auf HTTP\-spezifische Eigenschaften](../../../docs/framework/network-programming/how-to-access-http-specific-properties.md)