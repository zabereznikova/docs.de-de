---
title: 'FTP: .NET'
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
ms.openlocfilehash: d945f03077a863d9e1baa6b59fe8a908566aba5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "61642879"
---
# <a name="ftp"></a>FTP

.NET Framework bietet durch die Klassen <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> eine umfassende Unterstützung für das FTP-Protokoll. Diese Klassen werden von <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> abgeleitet. In den meisten Klassen stellen die Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> alles bereit, was für die Anforderung notwendig ist. Wenn Sie jedoch Zugriff auf die FTP-spezifischen Funktionen benötigen, die als Eigenschaften verfügbar gemacht werden, können Sie den Typ dieser Klassen zu <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> umwandeln.

## <a name="examples"></a>Beispiele

Weitere Informationen finden Sie in den folgenden Themen: [How to: Download Files with FTP (Vorgehensweise: Herunterladen von Dateien mit FTP)](how-to-download-files-with-ftp.md), [How to: Upload Files with FTP (Vorgehensweise: Hochladen von Dateien mit FTP)](how-to-upload-files-with-ftp.md) und [How to: List Directory Contents with FTP (Vorgehensweise: Auflisten von Verzeichnisinhalten mit FTP)](how-to-list-directory-contents-with-ftp.md).

## <a name="ftp-and-proxies"></a>FTP und Proxys

Wenn es sich bei einem Proxy (angegeben durch die <xref:System.Net.FtpWebRequest.Proxy%2A>-Eigenschaft) um einen HTTP-Proxy handelt, werden nur die <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>-, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>- und <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>-Befehle unterstützt.

## <a name="see-also"></a>Weitere Informationen

- [Accessing the Internet Through a Proxy (Zugreifen auf das Internet über einen Proxy)](accessing-the-internet-through-a-proxy.md)
- [Network Programming Samples (Beispiele zur Netzwerkprogrammierung)](network-programming-samples.md)
- [Using Application Protocols (Verwenden von Anwendungsprotokollen)](using-application-protocols.md)
