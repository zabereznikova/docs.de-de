---
title: Standard- und Digestauthentifizierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 7ca66a65c05da3d515358c0fdb26682fa4ec1438
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="basic-and-digest-authentication"></a>Standard- und Digestauthentifizierung
Die <xref:System.Net>-Implementierung der Standard- und Digestauthentifizierung entspricht der RFC2617 – HTTP-Authentifizierung: Standard- und Digestauthentifizierung (verfügbar auf der World Wide Web Consortium-Website unter www.w3.org).  
  
 Um Standard- und Digestauthentifizierung zu verwenden, muss eine Anwendung einen Benutzernamen und ein Kennwort in der <xref:System.Net.WebRequest.Credentials%2A>-Eigenschaft des <xref:System.Net.WebRequest>-Objekts bereitstellen, das zur Anforderung von Daten aus dem Internet verwendet wird, wie im folgenden Beispiel gezeigt.  
  
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
>  Mittels Standard- und Hashwertauthentifizierung gesendete Daten sind nicht verschlüsselt und daher für Angreifer sichtbar. Anmeldeinformationen für die Standardauthentifizierung (Benutzername und Kennwort) werden zudem in Klartext gesendet und können abgefangen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [NTLM- und Kerberos-Authentifizierung](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)  
 [Internet Authentication (Internetauthentifizierung)](../../../docs/framework/network-programming/internet-authentication.md)
