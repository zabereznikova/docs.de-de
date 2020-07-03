---
title: Anfordern von Daten
description: Hier erfahren Sie, wie Sie mit austauschbaren Protokollen Anwendungen entwickeln können, in denen über eine einzige Schnittstelle Daten aus mehreren Protokollen abgerufen werden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sending data
- WebRequest class, sending and receiving data
- requesting data from Internet, about requesting data
- WebClient class, sending and receiving data
- network, requesting data
- receiving data
- sending data, about sending data
- response to Internet request, about responding to Internet requests
- data requests
- receiving data, about receiving data
- Internet, requesting data
ms.assetid: df6f1e1d-6f2a-45dd-8141-4a85c3dafe1d
ms.openlocfilehash: 19350d685a81d56657ca0a117d61b50ae24fab6a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502183"
---
# <a name="requesting-data"></a>Anfordern von Daten
Um Anwendungen zu entwickeln, die in der verteilten Betriebssystemumgebung des heutigen Internets ausgeführt werden können, benötigen Sie eine effiziente und einfach zu nutzende Methode für das Abrufen von Daten aus Ressourcen aller Art. Mithilfe austauschbarer Protokolle lassen sich Anwendungen entwickeln, in denen über eine einzige Schnittstelle Daten aus mehreren Internetprotokollen abgerufen werden.  
  
## <a name="uploading-and-downloading-data-from-an-internet-server"></a>Hochladen und Herunterladen von Daten aus einem Internetserver  
 Für eine einfache Transaktion mit Anforderung und Antwort lassen sich mit der Klasse <xref:System.Net.WebClient> am einfachsten Daten auf einen Internetserver hoch- oder von ihm herunterzuladen. Die Klasse **WebClient** bietet Methoden für das Hoch- und Herunterladen von Dateien, für das Senden und Empfangen von Streams und für das Senden eines Datenpuffers an den Server und den Empfang einer Antwort. **WebClient** verwendet die Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse>, um die tatsächlichen Verbindungen zu den Internetressourcen herzustellen, damit jedes registrierte, austauschbare Protokoll genutzt werden kann.  
  
 Clientanwendungen, für die komplexere Transaktionen ausgeführt werden, fordern Daten mithilfe der Klasse **WebRequest** und ihren Nachfolgern von den Servern an. **WebRequest** kapselt die Details zum Aufbau der Serververbindung, zum Senden der Anforderung und zum Empfang der Nachricht ein. **WebRequest** ist eine abstrakte Klasse, die eine Reihe von Eigenschaften und Methoden definiert. Diese sind für alle Anwendungen verfügbar, die austauschbare Protokolle nutzen. Nachfolger von **WebRequest**, z.B. <xref:System.Net.HttpWebRequest>, implementieren die von **WebRequest** definierten Eigenschaften und Methoden konsistent zum zu Grunde liegenden Protokoll.  
  
 **WebRequest** erstellt protokollspezifische Instanzen von **WebRequest**-Nachfolgern. Hierfür wird mit den an die Methode <xref:System.Net.WebRequest.Create%2A> übergebenen Werten bestimmt, welche Instanz der abgeleiteten Klasse erstellt werden muss. Anwendungen geben an, welcher **WebRequest**-Nachfolger verwendet werden sollte, um eine Anforderung zu handeln. Dies geschieht durch die Registrierung des Nachfolgerkonstruktors mithilfe der Methode <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType>.  
  
 Für eine Anforderung an eine Internetressource wird die Methode <xref:System.Net.WebRequest.GetResponse%2A> der Klasse **WebRequest** aufgerufen. Die Methode **GetResponse** konstruiert die protokollspezifische Anforderung aus den Eigenschaften der **WebRequest**-Klasse, stellt die TCP- oder UDP-Socketverbindung zum Server her und sendet die Anforderung. Bei Anforderungen, im Rahmen derer Daten an einen Server gesendet werden, z.B. HTTP **Post** oder FTP **Put**, stellt die Methode <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> dafür einen Netzwerkstream bereit.  
  
 Die Methode **GetResponse** gibt eine protokollspezifische **WebResponse** zurück, die mit **WebRequest** übereinstimmt.  
  
 Die Klasse **WebResponse** ist ebenfalls eine abstrakte Klasse, die Eigenschaften und Methoden definiert, die für alle Anwendungen mit austauschbaren Protokollen verfügbar sind. **WebResponse**-Nachfolger implementieren diese Eigenschaften und Methoden für das zu Grunde liegende Protokoll. Beispielsweise implementiert die Klasse <xref:System.Net.HttpWebResponse> die **WebResponse**-Klasse für HTTP.  
  
 Die vom Server zurückgegebenen Daten sind für die Anwendung über den von der Methode <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> zurückgegebenen Stream verfügbar. Wie in den folgenden Beispielen gezeigt, lässt sich dieser Stream wie alle anderen auch verwenden.  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## <a name="see-also"></a>Siehe auch

- [Netzwerkprogrammierung in .NET Framework](index.md)
- [How to: Anfordern einer Webseite und Abrufen der Ergebnisse als Stream](how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)
- [How to: Abrufen einer protokollspezifischen WebResponse-Klasse, die einer WebRequest-Klasse entspricht](how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)
