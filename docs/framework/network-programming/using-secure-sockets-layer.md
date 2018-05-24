---
title: Verwenden von Secure Sockets Layer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Networking
- SSL
- Secure Sockets Layer
- requesting data from Internet, Secure Sockets Layer
- sending data, Secure Sockets Layer
- Network Resources
- data requests, Secure Sockets Layer
- receiving data, Secure Sockets Layer
- Internet, Secure Sockets Layer
ms.assetid: 6e4289e6-d1b7-4e82-ab0d-e83e3b6063ed
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2baedaa445f81e3e204f7414c5142232755581ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-secure-sockets-layer"></a>Verwenden von Secure Sockets Layer
Die <xref:System.Net>-Klassen verwenden Secure Sockets Layer (SSL) zum Verschlüsseln der Verbindung für mehrere Netzwerkprotokolle.  
  
 Für HTTP-Verbindungen verwenden die <xref:System.Net.WebRequest>- und <xref:System.Net.WebResponse>-Klassen SSL zur Kommunikation mit Webhosts, die SSL unterstützen. Die Entscheidung zur Verwendung von SSL erfolgt durch die <xref:System.Net.WebRequest>-Klasse, in Abhängigkeit vom erhaltenen URI. Wenn der URI mit „Https:“ beginnt, dann wird SSL verwendet. Beginnt der URI mit „Http:“, dann wird eine nicht verschlüsselte Verbindung verwendet.  
  
 Zur Verwendung von SSL mit File Transfer Protocol (FTP) legen Sie die <xref:System.Net.FtpWebRequest.EnableSsl>-Eigenschaft vor dem Aufruf von <xref:System.Net.FtpWebRequest.GetResponse> auf TRUE fest. Legen Sie zur Verwendung von SSL mit SMTP (Simple Mail Transport Protocol) die <xref:System.Net.Mail.SmtpClient.EnableSsl>-Eigenschaft auf TRUE fest, bevor Sie die E-Mail versenden.  
  
 Die <xref:System.Net.Security.SslStream>-Klasse stellt eine streambasierte Abstraktion für SSL zur Verfügung und bietet viele Möglichkeiten zum Konfigurieren des SSL-Handshakes.  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
  
```vb  
Dim MyURI As String = "https://www.contoso.com/"  
Dim Wreq As WebRequest = WebRequest.Create(MyURI)  
  
Dim serverUri As String = "ftp://ftp.contoso.com/file.txt"  
Dim request As FtpWebRequest = CType(WebRequest.Create(serverUri), FtpWebRequest)  
request.Method = WebRequestMethods.Ftp.DeleteFile  
request.EnableSsl = True  
Dim response As FtpWebResponse = CType(request.GetResponse(), FtpWebResponse)  
```  
  
```csharp  
String MyURI = "https://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
  
String serverUri = "ftp://ftp.contoso.com/file.txt"  
FtpWebRequest request = (FtpWebRequest)WebRequest.Create(serverUri);  
request.EnableSsl = true;  
request.Method = WebRequestMethods.Ftp.DeleteFile;  
FtpWebResponse response = (FtpWebResponse)request.GetResponse();  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf den Namespace **System.Net**  
  
## <a name="see-also"></a>Siehe auch  
 [Security in Network Programming (Sicherheit in der Netzwerkprogrammierung)](../../../docs/framework/network-programming/security-in-network-programming.md)  
 [Netzwerkprogrammierung in .NET Framework](../../../docs/framework/network-programming/index.md)  
 [Zertifikatauswahl und -überprüfung](../../../docs/framework/network-programming/certificate-selection-and-validation.md)
