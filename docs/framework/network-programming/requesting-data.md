---
title: "Anfordern von Daten | Microsoft Docs"
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
  - "Senden von Daten"
  - "WebRequest-Klasse, Senden und Empfangen von Daten"
  - "Anfordern von Daten aus dem Internet, Informationen zum Anfordern von Daten"
  - "WebClient-Klasse, Senden und Empfangen von Daten"
  - "Netzwerk, Anfordern von Daten"
  - "Empfangen von Daten"
  - "Senden von Daten, Informationen zum Senden von Daten"
  - "Antwort auf Internetanforderung, Informationen zum Reagieren auf Internetanforderungen"
  - "Datenanforderungen"
  - "Empfangen von Daten, Informationen zum Empfangen von Daten"
  - "Internet, Anfordern von Daten"
ms.assetid: df6f1e1d-6f2a-45dd-8141-4a85c3dafe1d
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Anfordern von Daten
Die Entwicklung von Anwendungen, die in die verteilte Betriebsumgebung für heute Internet ausgeführt werden, erfordert eine effiziente, benutzerfreundliche Methode für das Abrufen von Daten von Ressourcen aller Typen.  Austauschbare Protokolle können Sie Anwendungen entwickeln, die eine einzelne Schnittstelle verwenden, um Daten aus mehreren Internetprotokollen abzurufen.  
  
## Daten aus einem Internetserver Hochladen und Herunterladen von  
 Für einfache Anforderungen und Wartetransaktionen stellt die <xref:System.Net.WebClient>\-Klasse die einfachste Methode zum Hochladen von Daten zu und Herunterladen von Daten von einem Internetserver bereit.  **WebClient** stellt Methoden zum Hochladen und Herunterladen von Dateien, das Senden und Empfangen von Streams und das Senden eines Datenpuffers zum Server und Empfangen einer Antwort bereit.  **WebClient** verwendet die <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse>\-Klassen, um die tatsächlichen Beziehungen zur Internetressource zu erstellen, sodass jedes registrierte austauschbare Protokoll zur Verwendung verfügbar.  
  
 Clientanwendungen, die komplexere Transaktionen ausführen müssen, benötigen Daten von den Servern mithilfe der **WebRequest**\-Klasse und seiner Nachfolger.  **WebRequest** kapselt die Details der Verbindung zum Server, Senden der Anforderung und des Empfangens der Antwort.  **WebRequest** ist eine abstrakte Klasse, die einen Satz von Eigenschaften und Methoden definiert, die für alle Anwendungen verfügbar sind, die austauschbare Protokolle verwenden.  Nachfolger von **WebRequest**, wie <xref:System.Net.HttpWebRequest>, implementieren die Eigenschaften und Methoden, die von **WebRequest** so definiert werden, die mit dem zugrunde liegenden Protokoll konsistent ist.  
  
 Die **WebRequest**\-Klasse erstellt protokollspezifische Instanzen von **WebRequest** Nachfolgern, mit dem Wert des URI, das auf die <xref:System.Net.WebRequest.Create%2A>\-Methode übergeben wird, um bestimmte Instanz der abgeleiteten Klasse festzulegen, um zu erstellen.  Anwendungen geben an, die **WebRequest** Nachfolger verwendet werden soll, um eine Anforderung zu bearbeiten, indem Sie den Konstruktor des Nachfolgers mit der <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=fullName>\-Methode registriert.  
  
 Eine Anforderung an die Internetressource gemacht, indem die <xref:System.Net.WebRequest.GetResponse%2A>\-Methode auf **WebRequest** aufgerufen wird.  Die **GetResponse**\-Methode erstellt die protokollspezifische Anforderung von Eigenschaften **WebRequest**, stellt das TCP oder die UDP\-Socket\-Beziehung zum Server erstellt und sendet die Anforderung.  Für Anforderungen, die Daten auf dem Server, wie Anforderungen **Post** HTTP oder FTP **Put** senden, stellt die <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=fullName>\-Methode einen Netzwerkstream, in dem die Daten senden.  
  
 Die **GetResponse**\-Methode gibt eine protokollspezifische **WebResponse** zurück, die **WebRequest.** übereinstimmt  
  
 Die **WebResponse**\-Klasse ist auch eine abstrakte Klasse, die Eigenschaften und Methoden definiert, die für alle Anwendungen verfügbar sind, die austauschbare Protokolle verwenden.  **WebResponse** Nachfolger implementieren diese Eigenschaften und Methoden für das zugrunde liegende Protokoll.  Die <xref:System.Net.HttpWebResponse>\-Klasse beispielsweise implementiert die Klasse **WebResponse** für HTTP.  
  
 Die Daten, die vom Server zurückgegeben werden, werden der Anwendung im Stream präsentiert, der durch die <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=fullName>\-Methode zurückgegeben wird.  Sie können diesen Stream wie jeder andere, wie im folgenden Beispiel gezeigt.  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## Siehe auch  
 [Netzwerkprogrammierung in .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Gewusst wie: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream](../../../docs/framework/network-programming/how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)   
 [Gewusst wie: Abrufen eines protokollspezifischen WebResponse, das einem WebRequest entspricht](../../../docs/framework/network-programming/how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)