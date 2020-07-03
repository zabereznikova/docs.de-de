---
title: Bewährte Methoden für System.Net-Klassen
description: Halten Sie sich an die folgenden Empfehlungen zur optimalen Verwendung der in System.Net enthaltenen Klassen bei der .NET Framework-Programmierung.
ms.date: 03/30/2017
helpviewer_keywords:
- sending data, best practices
- requesting data from Internet, best practices
- WebRequest class, best practices
- data requests, best practices
- WebResponse class, best practices
- best practices, data requests
- receiving data, best practices
ms.assetid: 716decc6-5952-47b7-9c5a-ba6fc5698684
ms.openlocfilehash: 583fa5e57c7c4d60252dddfd425596e7acad7c0d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502677"
---
# <a name="best-practices-for-systemnet-classes"></a>Bewährte Methoden für System.Net-Klassen
Mit den folgenden Empfehlungen können Sie die in <xref:System.Net> enthaltenen Klassen bestmöglich verwenden:  
  
- Bewährte Methoden für Transport Layer Security (TLS) finden Sie unter [Bewährte Methoden für Transport Layer Security (TLS) mit .NET Framework](tls.md).

- Verwenden Sie nach Möglichkeit <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> anstelle der Typumwandlung in abgeleiteten Klassen. Anwendungen, die **WebRequest** und **WebResponse** verwenden, profitieren von neuen Internetprotokollen ohne umfangreiche Codeänderungen.  
  
- Beim Schreiben von ASP.NET-Anwendungen, die auf einem Server mit den **System.Net**-Klassen ausgeführt werden, ist es leistungstechnisch gesehen häufig besser, asynchrone Methoden für <xref:System.Net.WebRequest.GetResponse%2A> und <xref:System.Net.WebResponse.GetResponseStream%2A> zu verwenden.  
  
- Die Anzahl der offenen Verbindungen einer Internetressource haben einen erheblichen Einfluss auf die Netzwerkleistung und den Durchsatz. **System.Net** verwendet standardmäßig zwei Verbindungen pro Anwendung und pro Host. Das Festlegen der <xref:System.Net.ServicePoint.ConnectionLimit%2A>-Eigenschaft in <xref:System.Net.ServicePoint> für Ihre Anwendung kann diese Zahl für einen bestimmten Host erhöhen. Das Festlegen der <xref:System.Net.ServicePointManager.DefaultPersistentConnectionLimit?displayProperty=nameWithType>-Eigenschaft kann diese Standardeinstellung für alle Hosts erhöhen.  
  
- Beim Schreiben von Protokollen auf Socketebene versuchen Sie nach Möglichkeit <xref:System.Net.Sockets.TcpClient> oder <xref:System.Net.Sockets.UdpClient> zu verwenden, anstatt direkt <xref:System.Net.Sockets.Socket> zu schreiben. Diese zwei Clientklassen kapseln die Erstellung von TCP- und UDP-Sockets, ohne dass Sie die Details der Verbindung behandeln.  
  
- Verwenden Sie beim Zugriff auf Websites, die Anmeldeinformationen erfordern, die <xref:System.Net.CredentialCache>-Klasse zum Erstellen eines Zwischenspeichers für Anmeldeinformationen, anstatt sie mit jeder Anforderung bereitzustellen. Die **CredentialCache**-Klasse durchsucht den Zwischenspeicher nach den entsprechenden Anmeldeinformationen für eine Anforderung, sodass Sie keine Verantwortung für das Erstellen und Bereitstellen von Anmeldeinformationen auf Basis der URL haben.  
  
## <a name="see-also"></a>Siehe auch

- [Netzwerkprogrammierung in .NET Framework](index.md)
