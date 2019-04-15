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
ms.openlocfilehash: 2efb2d25e1b7566e3405a699be1795b37d549091
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183364"
---
# <a name="ntlm-and-kerberos-authentication"></a><span data-ttu-id="0be9f-102">NTLM- und Kerberos-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0be9f-102">NTLM and Kerberos Authentication</span></span>
<span data-ttu-id="0be9f-103">Die NTLM- und Kerberos-Authentifizierung verwendet standardmäßig die mit der aufrufenden Anwendung verbundenen Benutzeranmeldeinformationen von Microsoft Windows NT, um sich bei einem Server zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="0be9f-103">Default NTLM authentication and Kerberos authentication use the Microsoft Windows NT user credentials associated with the calling application to attempt authentication with the server.</span></span> <span data-ttu-id="0be9f-104">Bei der nicht standardmäßigen NTLM-Authentifizierung wird der Authentifizierungstyp durch die Anwendung auf NTLM festgelegt. Mithilfe des <xref:System.Net.NetworkCredential>-Objekts wird, wie im folgenden Beispiel gezeigt, der Benutzername, das Kennwort und die Domäne an den Host übergeben.</span><span class="sxs-lookup"><span data-stu-id="0be9f-104">When using non-default NTLM authentication, the application sets the authentication type to NTLM and uses a <xref:System.Net.NetworkCredential> object to pass the user name, password, and domain to the host, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="0be9f-105">Anwendungen, die sich mit den Anmeldeinformationen des Anwendungsbenutzers mit Internetdiensten verbinden müssen, können wie im folgenden Beispiel gezeigt über die Standardanmeldeinformationen des Benutzers verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="0be9f-105">Applications that need to connect to Internet services using the credentials of the application user can do so with the user's default credentials, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="0be9f-106">Mithilfe des Negotiate-Authentifizierungsmoduls wird bestimmt, ob der Remoteserver die NTLM- oder Kerberos-Authentifizierung verwendet, und es wird die entsprechende Antwort gesendet.</span><span class="sxs-lookup"><span data-stu-id="0be9f-106">The negotiate authentication module determines whether the remote server is using NTLM or Kerberos authentication, and sends the appropriate response.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0be9f-107">Die NTLM-Authentifizierung funktioniert nicht über einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="0be9f-107">NTLM authentication does not work through a proxy server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be9f-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0be9f-108">See also</span></span>

- [<span data-ttu-id="0be9f-109">Standard- und Digestauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="0be9f-109">Basic and Digest Authentication</span></span>](../../../docs/framework/network-programming/basic-and-digest-authentication.md)
- [<span data-ttu-id="0be9f-110">Internetauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="0be9f-110">Internet Authentication</span></span>](../../../docs/framework/network-programming/internet-authentication.md)
