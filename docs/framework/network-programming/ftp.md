---
title: FTP
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
ms.openlocfilehash: 0f35cb5c106d041a771d17a6e528cbbc1d38042b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187672"
---
# <a name="ftp"></a>FTP
.NET Framework bietet durch die Klassen <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> eine umfassende Unterstützung für das FTP-Protokoll. Diese Klassen werden von <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> abgeleitet. In den meisten Klassen stellen die Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> alles bereit, was für die Anforderung notwendig ist. Wenn Sie jedoch Zugriff auf die FTP-spezifischen Funktionen benötigen, die als Eigenschaften verfügbar gemacht werden, können Sie den Typ dieser Klassen zu <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> umwandeln.  
  
## <a name="examples"></a>Beispiele  
 Weitere Informationen finden Sie in den folgenden Themen: [How to: Download Files with FTP (Vorgehensweise: Herunterladen von Dateien mit FTP)](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [How to: Upload Files with FTP (Vorgehensweise: Hochladen von Dateien mit FTP)](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md) und [How to: List Directory Contents with FTP (Vorgehensweise: Auflisten von Verzeichnisinhalten mit FTP)](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).  
  
## <a name="ftp-and-proxies"></a>FTP und Proxys  
 Wenn es sich bei einem Proxy (angegeben durch die <xref:System.Net.FtpWebRequest.Proxy%2A>-Eigenschaft) um einen HTTP-Proxy handelt, werden nur die <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>-, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>- und <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>-Befehle unterstützt.  
  
## <a name="see-also"></a>Siehe auch  
 [Zugreifen auf das Internet über einen Proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)  
 [Beispiel zur FTP-Clienttechnologie](https://go.microsoft.com/fwlink/?LinkID=179557)  
 [Beispiel zur FTP-Explorer-Technologie](https://go.microsoft.com/fwlink/?LinkID=179569)  
 [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)
