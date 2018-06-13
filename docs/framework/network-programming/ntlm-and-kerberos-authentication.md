---
title: NTLM- und Kerberos-Authentifizierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], NTLM
- authentication [.NET Framework], Kerberos
- user authentication, Kerberos
- user authentication, NTLM
- Kerberos authentication
- receiving data, authentication
- NTLM authentication
- Internet, authentication
- client authentication, Kerberos
- sending data, authentication
- network resources, authentication
- classes [.NET Framework], authentication
- client authentication, NTLM
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d1f621af2b365d229b7b5e62069471af98be267a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33394386"
---
# <a name="ntlm-and-kerberos-authentication"></a><span data-ttu-id="45ae0-102">NTLM- und Kerberos-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="45ae0-102">NTLM and Kerberos Authentication</span></span>
<span data-ttu-id="45ae0-103">Die NTLM- und Kerberos-Authentifizierung verwendet standardmäßig die mit der aufrufenden Anwendung verbundenen Benutzeranmeldeinformationen von Microsoft Windows NT, um sich bei einem Server zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="45ae0-103">Default NTLM authentication and Kerberos authentication use the Microsoft Windows NT user credentials associated with the calling application to attempt authentication with the server.</span></span> <span data-ttu-id="45ae0-104">Bei der nicht standardmäßigen NTLM-Authentifizierung wird der Authentifizierungstyp durch die Anwendung auf NTLM festgelegt. Mithilfe des <xref:System.Net.NetworkCredential>-Objekts wird, wie im folgenden Beispiel gezeigt, der Benutzername, das Kennwort und die Domäne an den Host übergeben.</span><span class="sxs-lookup"><span data-stu-id="45ae0-104">When using non-default NTLM authentication, the application sets the authentication type to NTLM and uses a <xref:System.Net.NetworkCredential> object to pass the user name, password, and domain to the host, as shown in the following example.</span></span>  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = _  
    New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials =   
    new NetworkCredential(UserName, SecurelyStoredPassword, Domain);  
```  
  
 <span data-ttu-id="45ae0-105">Anwendungen, die sich mit den Anmeldeinformationen des Anwendungsbenutzers mit Internetdiensten verbinden müssen, können wie im folgenden Beispiel gezeigt über die Standardanmeldeinformationen des Benutzers verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="45ae0-105">Applications that need to connect to Internet services using the credentials of the application user can do so with the user's default credentials, as shown in the following example.</span></span>  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = CredentialCache.DefaultCredentials  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials = CredentialCache.DefaultCredentials;  
```  
  
 <span data-ttu-id="45ae0-106">Mithilfe des Negotiate-Authentifizierungsmoduls wird bestimmt, ob der Remoteserver die NTLM- oder Kerberos-Authentifizierung verwendet, und es wird die entsprechende Antwort gesendet.</span><span class="sxs-lookup"><span data-stu-id="45ae0-106">The negotiate authentication module determines whether the remote server is using NTLM or Kerberos authentication, and sends the appropriate response.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45ae0-107">Die NTLM-Authentifizierung funktioniert nicht über einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="45ae0-107">NTLM authentication does not work through a proxy server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ae0-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45ae0-108">See Also</span></span>  
 [<span data-ttu-id="45ae0-109">Standard- und Digestauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="45ae0-109">Basic and Digest Authentication</span></span>](../../../docs/framework/network-programming/basic-and-digest-authentication.md)  
 [<span data-ttu-id="45ae0-110">Internet Authentication (Internetauthentifizierung)</span><span class="sxs-lookup"><span data-stu-id="45ae0-110">Internet Authentication</span></span>](../../../docs/framework/network-programming/internet-authentication.md)
