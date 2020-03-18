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
ms.openlocfilehash: ef2abc7574aea1b4f77ff93545ad84678c66ce48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71046905"
---
# <a name="using-secure-sockets-layer"></a><span data-ttu-id="b17ce-102">Verwenden von Secure Sockets Layer</span><span class="sxs-lookup"><span data-stu-id="b17ce-102">Using Secure Sockets Layer</span></span>
<span data-ttu-id="b17ce-103">Die <xref:System.Net>-Klassen verwenden Secure Sockets Layer (SSL) zum Verschlüsseln der Verbindung für mehrere Netzwerkprotokolle.</span><span class="sxs-lookup"><span data-stu-id="b17ce-103">The <xref:System.Net> classes use the Secure Sockets Layer (SSL) to encrypt the connection for several network protocols.</span></span>  
  
 <span data-ttu-id="b17ce-104">Für HTTP-Verbindungen verwenden die <xref:System.Net.WebRequest>- und <xref:System.Net.WebResponse>-Klassen SSL zur Kommunikation mit Webhosts, die SSL unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b17ce-104">For http connections, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes use SSL to communicate with web hosts that support SSL.</span></span> <span data-ttu-id="b17ce-105">Die Entscheidung zur Verwendung von SSL erfolgt durch die <xref:System.Net.WebRequest>-Klasse, in Abhängigkeit vom erhaltenen URI.</span><span class="sxs-lookup"><span data-stu-id="b17ce-105">The decision to use SSL is made by the <xref:System.Net.WebRequest> class, based on the URI it is given.</span></span> <span data-ttu-id="b17ce-106">Wenn der URI mit „Https:“ beginnt, dann wird SSL verwendet. Beginnt der URI mit „Http:“, dann wird eine nicht verschlüsselte Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b17ce-106">If the URI begins with "https:", SSL is used; if the URI begins with "http:", an unencrypted connection is used.</span></span>  
  
 <span data-ttu-id="b17ce-107">Zur Verwendung von SSL mit File Transfer Protocol (FTP) legen Sie die <xref:System.Net.FtpWebRequest.EnableSsl>-Eigenschaft vor dem Aufruf von <xref:System.Net.FtpWebRequest.GetResponse> auf TRUE fest.</span><span class="sxs-lookup"><span data-stu-id="b17ce-107">To use SSL with File Transfer Protocol (FTP), set the <xref:System.Net.FtpWebRequest.EnableSsl> property to true prior to calling <xref:System.Net.FtpWebRequest.GetResponse>.</span></span> <span data-ttu-id="b17ce-108">Legen Sie zur Verwendung von SSL mit SMTP (Simple Mail Transport Protocol) die <xref:System.Net.Mail.SmtpClient.EnableSsl>-Eigenschaft auf TRUE fest, bevor Sie die E-Mail versenden.</span><span class="sxs-lookup"><span data-stu-id="b17ce-108">Similarly, to use SSL with Simple Mail Transport Protocol (SMTP), set the <xref:System.Net.Mail.SmtpClient.EnableSsl> property to true prior to sending the email.</span></span>  
  
 <span data-ttu-id="b17ce-109">Die <xref:System.Net.Security.SslStream>-Klasse stellt eine streambasierte Abstraktion für SSL zur Verfügung und bietet viele Möglichkeiten zum Konfigurieren des SSL-Handshakes.</span><span class="sxs-lookup"><span data-stu-id="b17ce-109">The <xref:System.Net.Security.SslStream> class provides a stream-based abstraction for SSL, and offers many ways to configure the SSL handshake.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b17ce-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b17ce-110">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="b17ce-111">Code</span><span class="sxs-lookup"><span data-stu-id="b17ce-111">Code</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="b17ce-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b17ce-112">Compiling the Code</span></span>  
 <span data-ttu-id="b17ce-113">Dieses Beispiel erfordert Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b17ce-113">This example requires:</span></span>  
  
- <span data-ttu-id="b17ce-114">Verweise auf den Namespace **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="b17ce-114">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b17ce-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b17ce-115">See also</span></span>

- [<span data-ttu-id="b17ce-116">Security in Network Programming (Sicherheit in der Netzwerkprogrammierung)</span><span class="sxs-lookup"><span data-stu-id="b17ce-116">Security in Network Programming</span></span>](security-in-network-programming.md)
- [<span data-ttu-id="b17ce-117">Netzwerkprogrammierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b17ce-117">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="b17ce-118">Zertifikatauswahl und -überprüfung</span><span class="sxs-lookup"><span data-stu-id="b17ce-118">Certificate Selection and Validation</span></span>](certificate-selection-and-validation.md)
