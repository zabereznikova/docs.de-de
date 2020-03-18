---
title: Standard- und Digestauthentifizierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], classes
- Basic authentication
- authentication [.NET Framework], basic
- client authentication, basic
- user authentication, basic
- authentication [.NET Framework], digest
- receiving data, authentication
- client authentication, digest
- Internet, authentication
- digest authentication
- sending data, authentication
- network resources, authentication
- user authentication, digest
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
ms.openlocfilehash: 9a1ad701e1e8f4ee9966ebd56922c29e2bae7a03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048902"
---
# <a name="basic-and-digest-authentication"></a><span data-ttu-id="24c72-102">Standard- und Digestauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="24c72-102">Basic and Digest Authentication</span></span>
<span data-ttu-id="24c72-103">Die <xref:System.Net>-Implementierung der Standard- und Digestauthentifizierung entspricht der RFC2617 – HTTP-Authentifizierung: Standard- und Digestauthentifizierung (verfügbar auf der Website des [World Wide Web Consortium (W3C)](https://www.w3.org)).</span><span class="sxs-lookup"><span data-stu-id="24c72-103">The <xref:System.Net> implementation of basic and digest authentication complies with RFC2617 – HTTP Authentication: Basic and Digest Authentication (available on the [World Wide Web Consortium's](https://www.w3.org) website).</span></span>  
  
 <span data-ttu-id="24c72-104">Um Standard- und Digestauthentifizierung zu verwenden, muss eine Anwendung einen Benutzernamen und ein Kennwort in der <xref:System.Net.WebRequest.Credentials%2A>-Eigenschaft des <xref:System.Net.WebRequest>-Objekts bereitstellen, das zur Anforderung von Daten aus dem Internet verwendet wird, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="24c72-104">To use basic and digest authentication, an application must provide a user name and password in the <xref:System.Net.WebRequest.Credentials%2A> property of the <xref:System.Net.WebRequest> object that it uses to request data from the Internet, as shown in the following example.</span></span>  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
WReq.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword);  
```  
  
> [!CAUTION]
> <span data-ttu-id="24c72-105">Mittels Standard- und Hashwertauthentifizierung gesendete Daten sind nicht verschlüsselt und daher für Angreifer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="24c72-105">Data sent with Basic and Digest Authentication is not encrypted, so the data can be seen by an adversary.</span></span> <span data-ttu-id="24c72-106">Anmeldeinformationen für die Standardauthentifizierung (Benutzername und Kennwort) werden zudem in Klartext gesendet und können abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="24c72-106">Additionally, Basic Authentication credentials (user name and password) are sent in the clear and can be intercepted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c72-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24c72-107">See also</span></span>

- [<span data-ttu-id="24c72-108">NTLM- und Kerberos-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="24c72-108">NTLM and Kerberos Authentication</span></span>](ntlm-and-kerberos-authentication.md)
- [<span data-ttu-id="24c72-109">Internet Authentication (Internetauthentifizierung)</span><span class="sxs-lookup"><span data-stu-id="24c72-109">Internet Authentication</span></span>](internet-authentication.md)
