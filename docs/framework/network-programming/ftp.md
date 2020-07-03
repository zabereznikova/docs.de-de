---
title: 'FTP: .NET'
description: Hier erfahren Sie mehr über die umfassende Unterstützung für das FTP-Protokoll, das das .NET Framework mithilfe der Klassen „FtpWebRequest“ und „FtpWebResponse“ bereitstellt.
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
ms.openlocfilehash: d21ca43cd1041df358dc5e2add9560fb33e85d83
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502586"
---
# <a name="ftp"></a>FTP

.NET Framework bietet durch die Klassen <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> eine umfassende Unterstützung für das FTP-Protokoll. Diese Klassen werden von <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> abgeleitet. In den meisten Klassen stellen die Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> alles bereit, was für die Anforderung notwendig ist. Wenn Sie jedoch Zugriff auf die FTP-spezifischen Funktionen benötigen, die als Eigenschaften verfügbar gemacht werden, können Sie den Typ dieser Klassen zu <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> umwandeln.

## <a name="examples"></a>Beispiele

Weitere Informationen finden Sie unter den folgenden Themen: [How to: Herunterladen von Dateien über FTP](how-to-download-files-with-ftp.md), [Vorgehensweise: Hochladen von Dateien über FTP](how-to-upload-files-with-ftp.md) und [Vorgehensweise: Auflisten von Verzeichnisinhalt mit FTP](how-to-list-directory-contents-with-ftp.md).

## <a name="ftp-and-proxies"></a>FTP und Proxys

Wenn es sich bei einem Proxy (angegeben durch die <xref:System.Net.FtpWebRequest.Proxy%2A>-Eigenschaft) um einen HTTP-Proxy handelt, werden nur die <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>-, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>- und <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>-Befehle unterstützt.

## <a name="see-also"></a>Siehe auch

- [Zugreifen auf das Internet über einen Proxy](accessing-the-internet-through-a-proxy.md)
- [Beispiele zur Netzwerkprogrammierung](network-programming-samples.md)
- [Verwenden von Anwendungsprotokollen](using-application-protocols.md)
