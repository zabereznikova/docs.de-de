---
title: Erstellen von Internetanforderungen
description: Erfahren Sie, wie Anwendungen WebRequest-Instanzen über die Methode WebRequest.Create erstellen, die eine abgeleitete Klasse auf Grundlage des an sie übergebenen URI-Schemas erstellt.
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
ms.openlocfilehash: 389c7bf5969eca4322aa680a6f28dec0b899709a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325641"
---
# <a name="create-internet-requests"></a>Erstellen von Internetanforderungen

Anwendungen erstellen mithilfe der <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>-Methode <xref:System.Net.WebRequest>-Instanzen. <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> ist eine statische Methode, die eine von <xref:System.Net.WebRequest> abgeleitete Klasse basierend auf dem an sie übergebenen URI-Schema erstellt.  
  
## <a name="web-file-and-ftp-requests"></a>Web- und Dateianforderungen sowie FTP-Anforderungen

Das .NET Framework stellt die von `WebRequest` abgeleitete Klasse <xref:System.Net.HttpWebRequest> bereit, um HTTP- und HTTPS-Anforderungen zu verarbeiten. In den meisten Fällen stellt die Klasse `WebRequest` alle für eine Anforderung erforderlichen Eigenschaften bereit. Bei Bedarf können Sie jedoch von der Methode `WebRequest.Create` erstellte `WebRequest`-Objekte in den Typ `HttpWebRequest` umwandeln, um auf die HTTP-spezifischen Eigenschaften der Anforderung zuzugreifen. Auf ähnliche Weise werden die Antworten auf HTTP- und HTTPS-Anforderungen durch das `HttpWebResponse`-Objekt verarbeitet. Sie müssen `WebResponse`-Objekte in den Typ `HttpWebResponse` umwandeln, um auf die HTTP-spezifischen Eigenschaften des `HttpWebResponse`-Objekts zugreifen zu können.  
  
Das .NET Framework stellt außerdem die Klassen <xref:System.Net.FileWebRequest> und <xref:System.Net.FileWebResponse> zum Verarbeiten von Anforderungen für Ressourcen bereit, die das URI-Schema „file:“ verwenden. Dementsprechend werden die Klassen <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> zur Verarbeitung von Anforderungen für Ressourcen bereitgestellt, die das Schema „ftp:“ verwenden. Bei Anforderungen für eine Ressource, die eines dieser Schemas verwendet, können Sie mithilfe der Methode `WebRequest.Create` ein Objekt abrufen, das Sie für die Anforderung verwenden können.  
  
Implementieren Sie von `WebRequest` und `WebResponse` abgeleitete protokollspezifische Klassen, um Anforderungen zu verarbeiten, die andere Protokolle auf Anwendungsebene verwenden. Weitere Informationen finden Sie unter [Programming Pluggable Protocols (Programmieren austauschbarer Protokolle)](programming-pluggable-protocols.md).  
  
## <a name="see-also"></a>Siehe auch

- [How to: Anfordern von Daten mithilfe der WebRequest-Klasse](how-to-request-data-using-the-webrequest-class.md)
- [Requesting Data (Anfordern von Daten)](requesting-data.md)
