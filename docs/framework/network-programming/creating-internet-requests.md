---
title: Erstellen von Internetanforderungen
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, sending and receiving data
- Networking
- HttpWebResponse class, sending and receiving data
- requesting data from Internet, creating requests
- Network Resources
- Internet, requesting data
- data requests, creating requests
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
ms.openlocfilehash: 80e3a6bd199691df9391e88d5a64fab5df2a08a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048622"
---
# <a name="creating-internet-requests"></a>Erstellen von Internetanforderungen
Anwendungen erstellen mithilfe der <xref:System.Net.WebRequest>-Methode <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>-Instanzen. Diese statische Methode erstellt eine von **WebRequest** abgeleitete Klasse basierend auf dem URI-Schema, das an sie übergeben wurde.  
  
## <a name="web-file-and-ftp-requests"></a>Web-, Datei- und FTP-Anforderungen  
 .NET Framework stellt die von <xref:System.Net.HttpWebRequest>WebRequest**abgeleitete**-Klasse bereit, um HTTP- und HTTPS-Anforderungen zu verarbeiten. In den meisten Fällen stellt die **WebRequest**-Klasse alle für eine Anforderung erforderlichen Eigenschaften bereit. Bei Bedarf können Sie jedoch mit der **WebRequest.Create**-Methode erstellte **WebRequest**-Objekte in den Typ **HttpWebRequest** umwandeln, um auf die HTTP-spezifischen Eigenschaften der Anforderung zuzugreifen. Auf ähnliche Weise werden die Antworten von HTTP- und HTTPS-Anforderungen durch das **HttpWebResponse**-Objekt verarbeitet. Wenn Sie auf die HTTP-spezifischen Eigenschaften des **HttpWebResponse**-Objekts zugreifen möchten, müssen Sie **WebResponse**-Objekte in den Typ **HttpWebResponse** umwandeln.  
  
 .NET Framework stellt außerdem die Klassen <xref:System.Net.FileWebRequest> und <xref:System.Net.FileWebResponse> zum Verarbeiten von Anforderungen für Ressourcen bereit, die das URI-Schema „file:“ verwenden. Dementsprechend werden die Klassen <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> zur Verarbeitung von Anforderungen für Ressourcen bereitgestellt, die das Schema „ftp:“ verwenden. Bei Anforderungen für eine Ressource, die eines dieser Schemas verwendet, können Sie mithilfe der **WebRequest.Create**-Methode ein Objekt abrufen, mit dem Sie die Anforderung erstellen können.  
  
 Bei Anforderungen, die andere Protokolle auf Anwendungsebene verwenden, müssen Sie von **WebRequest** und **WebResponse** abgeleitete protokollspezifische Klassen implementieren. Weitere Informationen finden Sie unter [Programming Pluggable Protocols (Programmieren austauschbarer Protokolle)](programming-pluggable-protocols.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Anfordern von Daten mithilfe der WebRequest-Klasse](how-to-request-data-using-the-webrequest-class.md)
- [Anfordern von Daten](requesting-data.md)
