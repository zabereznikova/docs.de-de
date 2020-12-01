---
title: Standard- und Digestauthentifizierung
description: Hier erfahren Sie, wie Sie die Standard- und Hashauthentifizierung verwenden, bei denen eine Anwendung einen Benutzernamen und ein Kennwort im WebRequest-Objekt bereitstellt, die zum Anfordern von Daten verwendet werden.
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
ms.openlocfilehash: e55dc58a7998824dbcfffa204008aacb815be03a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287578"
---
# <a name="basic-and-digest-authentication"></a><span data-ttu-id="04d8c-103">Standard- und Digestauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="04d8c-103">Basic and Digest Authentication</span></span>

<span data-ttu-id="04d8c-104">Die <xref:System.Net>-Implementierung der einfachen und Digestauthentifizierung entspricht dem Dokument zur HTTP-Authentifizierung RCF 2617: „Basic and Digest Authentication“ (Einfache und Digestauthentifizierung), das auf der Website des [World Wide Web Consortium](https://www.w3.org) zum Download zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="04d8c-104">The <xref:System.Net> implementation of basic and digest authentication complies with RFC2617 – HTTP Authentication: Basic and Digest Authentication (available on the [World Wide Web Consortium's](https://www.w3.org) website).</span></span>  
  
 <span data-ttu-id="04d8c-105">Um Standard- und Digestauthentifizierung zu verwenden, muss eine Anwendung einen Benutzernamen und ein Kennwort in der <xref:System.Net.WebRequest.Credentials%2A>-Eigenschaft des <xref:System.Net.WebRequest>-Objekts bereitstellen, das zur Anforderung von Daten aus dem Internet verwendet wird, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="04d8c-105">To use basic and digest authentication, an application must provide a user name and password in the <xref:System.Net.WebRequest.Credentials%2A> property of the <xref:System.Net.WebRequest> object that it uses to request data from the Internet, as shown in the following example.</span></span>  
  
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
> <span data-ttu-id="04d8c-106">Mittels Standard- und Hashwertauthentifizierung gesendete Daten sind nicht verschlüsselt und daher für Angreifer sichtbar.</span><span class="sxs-lookup"><span data-stu-id="04d8c-106">Data sent with Basic and Digest Authentication is not encrypted, so the data can be seen by an adversary.</span></span> <span data-ttu-id="04d8c-107">Anmeldeinformationen für die Standardauthentifizierung (Benutzername und Kennwort) werden zudem in Klartext gesendet und können abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="04d8c-107">Additionally, Basic Authentication credentials (user name and password) are sent in the clear and can be intercepted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04d8c-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04d8c-108">See also</span></span>

- [<span data-ttu-id="04d8c-109">NTLM- und Kerberos-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="04d8c-109">NTLM and Kerberos Authentication</span></span>](ntlm-and-kerberos-authentication.md)
- [<span data-ttu-id="04d8c-110">Internet Authentication (Internetauthentifizierung)</span><span class="sxs-lookup"><span data-stu-id="04d8c-110">Internet Authentication</span></span>](internet-authentication.md)
