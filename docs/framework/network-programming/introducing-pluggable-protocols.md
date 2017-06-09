---
title: "Einf&#252;hrung in austauschbare Protokolle | Microsoft Docs"
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
  - "Datenanforderungen, austauschbare Protokolle"
  - "WebRequest -Klasse, austauschbare Protokolle"
  - "Antwort auf Internetanforderung, austauschbare Protokolle"
  - "URI"
  - "Windows-Sockets"
  - "Anforderungs-/Antwortmodell"
  - "Senden von Daten, austauschbare Protokolle"
  - "austauschbare Protokolle"
  - "WebClient-Klasse, Informationen zur WebClient-Klasse"
  - "austauschbare Protokolle, Informationen zu austauschbaren Protokollen"
  - "Internet, austauschbare Protokolle"
  - "Pfadbezeichner"
  - "Uniform Resource Identifier"
  - "Anwendungsentwicklung [.NET Framework], austauschbare Protokolle"
  - "Anfordern von Daten aus dem Internet, austauschbare Protokolle"
  - "Empfangen von Daten, austauschbare Protokolle"
  - "Protokolle, austauschbare"
  - "Serverbezeichner"
  - "Schemabezeichner"
ms.assetid: 4b48e22d-e4e5-48f0-be80-d549bda97415
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Einf&#252;hrung in austauschbare Protokolle
Microsoft.NET Framework stellt eine überlappende, erweiterbare und verwaltete Implementierung mit Internetdiensten, die schnell und auf einfache Weise in Anwendungen integriert werden können.  Die Internetzugriffsklassen in <xref:System.Net> und <xref:System.Net.Sockets>\-Namespaces können verwendet werden, um die webbasierten und internetbasierten Anwendungen zu implementieren.  
  
## Internetanwendungen  
 Internetanwendungen können in zwei Arten von breit klassifiziert werden: Clientanwendungen, die anfordern, Informationen und Serveranwendungen, die auf Informationen reagieren, fordert von Clients an.  Die klassische Internet\-Clientserveranwendung ist das World Wide Web, in dem Personen Browser verwenden, um die Dokumente und auf andere Daten zuzugreifen, die weltweit auf Webservern gespeichert werden.  
  
 Anwendungen werden erst nur eine dieser Rollen beschränkt; beispielsweise reagiert der vertrauten Anwendungsserver der mittleren Ebene auf Anforderungen von Clients durch Anfordern von Daten von einem anderen Server, in diesem Fall wird als ein Server und einem Client auftritt.  
  
 Die Clientanwendung stellt eine Anforderung, indem sie die angeforderte Internetressource und das Kommunikationsprotokoll zur Verwendung für die Anforderung und die Antwort identifiziert.  ggf. stellt der Client auch zusätzliche Daten bereit, die erforderlich sind, um die Anforderung, wie Proxyspeicherort oder Authentifizierungsinformationen \(Benutzername, Kennwort, usw.\). abzuschließen.  Sobald die Anforderung, kann die Anforderung an den Server übermittelt werden gebildet.  
  
## Identifizieren von Ressourcen  
 . .NET Framework verwendet einen URI \(Uniform Resource Identifier\) der angeforderten Internetressource und das Kommunikationsprotokoll zu identifizieren.  Der URI besteht aus mindestens drei und möglicherweise aus vier, Fragmente: der Schemabezeichner, der das Kommunikationsprotokoll für die Anforderung und die Antwort angibt, dem Serverbezeichner, der entweder einen Hostnamen \(Domain Name System\) oder aus einer TCP\-Adresse besteht, die eindeutig den Server im Internet angibt, dem Pfadbezeichner, der die angeforderten Informationen zum Server darüber ermittelt; und eine optionale Abfragezeichenfolge, die Informationen vom Client zum Server übergibt.  Zum Beispiel besteht das URI "http:\/\/www.contoso.com\/whatsnew.aspx?date\=today" "http" aus des Schemabezeichners, dem Serverbezeichner "www.contoso.com", der Pfad "\/whatsnew.aspx" und die Abfragezeichenfolge "? date\=today".  
  
 Wenn der Server die Anforderung empfangen und die Antwort verarbeitet hat, wird die Antwort auf die Clientanwendung zurück.  Die Antwort enthält zusätzliche Informationen, wie der Typ des Inhalts \(unformatierten Text oder XML\-Daten, beispielsweise\).  
  
## Anforderungen und Antworten in .NET Framework  
 Die einzelnen Klassen .NET Framework\-Verwendung, um die drei Informationen bereitzustellen erforderlich, um auf Internetressourcen über ein Anforderungs\-\/Antwortmodell zuzugreifen: <xref:System.Uri> die Klasse, die den URI der Internetressource enthält, suchen Sie; <xref:System.Net.WebRequest> die Klasse, die eine Anforderung für die Ressource enthält; <xref:System.Net.WebResponse> und die Klasse, die einen Container für die eingehende Antwort bereitstellt.  
  
 Clientanwendungen erstellen `WebRequest`\-Instanzen, indem sie den URI der Netzwerkressource zur <xref:System.Net.WebRequest.Create%2A>\-Methode übergeben.  Diese statische Methode erstellt `WebRequest` für ein bestimmtes Protokoll, wie HTTP.  `WebRequest`, das zurückgegeben wird, ermöglicht den Zugriff auf Eigenschaften, die die Anforderung an den Server und den Zugriff auf den Datenstream steuern, der gesendet wird, wenn die Anforderung gestellt wird.  Die <xref:System.Net.WebRequest.GetResponse%2A>\-Methode auf `WebRequest` sendet die Anforderung von der Clientanwendung an den Server, der im URI angegeben wird.  In den Fällen, in denen die Antwort möglicherweise verzögert wird, kann die Anforderung mithilfe der <xref:System.Net.WebRequest.BeginGetResponse%2A>\-Methode auf **WebRequest** asynchron ausgeführt werden, und die Antwort kann mithilfe der <xref:System.Net.WebRequest.EndGetResponse%2A>\-Methode zu einem späteren Zeitpunkt zurückgegeben werden.  
  
 Die **GetResponse**  und **EndGetResponse**\-Methoden geben **WebResponse** zurück, das Zugriff auf die Daten ermöglicht, die vom Server zurückgegeben werden.  Da diese Daten zur anfordernde Anwendung als Stream auf die <xref:System.Net.WebResponse.GetResponseStream%2A>\-Methoden bereitgestellt werden, kann es in den Datenstreams einer Anwendung an jeder Stelle verwendet werden wird verwendet.  
  
 Die **WebRequest** und **WebResponse**\-Klassen sind die Grundlage von austauschbaren Protokollen \- eine Implementierung von Netzwerkdiensten, die Ihnen ermöglicht, um Anwendungen zu entwickeln, die Internetressourcen verwenden, ohne die spezifischen Details des Protokolls verloren gehen, das jede Ressource verwendet.  Nachfolgerklassen von **WebRequest** werden mit der **WebRequest**\-Klasse registriert, um die Details beim Erstellen der tatsächlichen Beziehungen zu den Internetressourcen zu verwalten.  
  
 Als Beispiel verwaltet die <xref:System.Net.HttpWebRequest>\-Klasse die Details einer Verbindung mit einer Internetressource mit HTTP.  Standardmäßig **WebRequest.Create** wenn die Methode einen URI trifft, die mit "HTTP beginnt: " oder "https: " \(die Protokollkennungen für HTTP und sicheres HTTP\), kann **WebRequest**, das zurückgegeben wird, verwendet werden, wie oder es kann der Typ zu **HttpWebRequest**, um auf protokollspezifische Eigenschaften zuzugreifen.  In den meisten Fällen bietet **WebRequest** alle erforderlichen Informationen für das Erstellen eines Antrags bereit.  
  
 Jedes Protokoll, das als Anforderung\/Wartetransaktion dargestellt werden kann, kann in **WebRequest** verwendet werden.  Sie können protokollspezifische Klassen von **WebRequest** und von **WebResponse**  ableiten und diese für die Anwendung mit der statischen <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=fullName>\-Methode dann registrieren.  
  
 Wenn Clientautorisierung für Internet\-Anforderungen erforderlich ist, stellt die <xref:System.Net.WebRequest.Credentials%2A>\-Eigenschaft **WebRequest** die erforderlichen Anmeldeinformationen.  Diese Anmeldeinformationen können einfache Name\/Kennwort\-Paare für ein grundlegendes HTTP oder Digestauthentifizierung oder ein Name\/Kennwort\/eine Domäne angehören, die für NTLM\- oder Kerberos\-Authentifizierung festgelegt ist.  Ein Satz von Anmeldeinformationen kann in einer Instanz [NetworkCredentials](frlrfsystemnetnetworkcredentialclasstopic) gespeichert werden, oder mehrere Sätze können in einer <xref:System.Net.CredentialCache>\-Instanz gleichzeitig gespeichert werden.  **CredentialCache** verwendet den URI der Anforderung und des Authentifizierungsschemas, das der Server unterstützt, um zu bestimmen, der an den Server zu senden, die Anmeldeinformationen.  
  
## Einfache Anforderungen mit web client  
 Für Anwendungen, die einfache Anforderungen für Internetressourcen senden müssen, stellt die <xref:System.Net.WebClient>\-Klasse allgemeine Methoden für das Hochladen von Daten an und Herunterladen von Daten von einem Internetserver bereit.  **WebClient** beruht auf der **WebRequest**\-Klasse, um den Zugriff auf Internetressourcen; Daher kann die Klasse **WebClient** jedes registrierte austauschbare Protokoll verwenden.  
  
 Für Anwendungen, die die Anforderung nicht verwenden können\/Anforderungs\-\/Antwortmodell oder für Anwendungen, die das Netzwerk überwachen müssen sowie Anforderungen zu senden, der **System.Net.Sockets**\-Namespace die [TCPClient](frlrfsystemnetsocketstcpclientclasstopic), [TCPListener](frlrfsystemnetsocketstcplistenerclasstopic) und [UDPClient](frlrfsystemnetsocketsudpclientclasstopic)\-Klassen bereitstellt.  Diese Klassen kümmern sich um die Details beim Erstellen der Verbindung. Sie verwenden dazu verschiedene Übertragungsprotokolle und machen die Netzwerkverbindung der Anwendung als Stream verfügbar.  
  
 Entwickler, die mit der Windows Socket\-Schnittstelle vertraut sind oder die, die das Steuerelement benötigen, das von der Programmierung auf der Socketebene bereitgestellt wird, feststellen, dass die **System.Net.Sockets**\-Klassen ihre Anforderungen erfüllen.  Die **System.Net.Sockets**\-Klassen sind ein Übergangspunkt von verwaltetem zu systemeigenem Code innerhalb der **System.Net**\-Klassen.  In den meisten Fällen marshallen **System.Net.Sockets**\-Klassen Daten in ihre Windows\-32\-Bit\-Entsprechungen behandeln sowie alle notwendigen Sicherheitsüberprüfungen.  
  
## Siehe auch  
 [Programmieren austauschbarer Protokolle](../../../docs/framework/network-programming/programming-pluggable-protocols.md)   
 [Netzwerkprogrammierung in .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Netzwerkfunktionens\-Beispiele für .NET auf MSDN Code Gallery](http://code.msdn.microsoft.com/Wiki/View.aspx?ProjectName=nclsamples)