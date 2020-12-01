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
# <a name="basic-and-digest-authentication"></a>Standard- und Digestauthentifizierung

Die <xref:System.Net>-Implementierung der einfachen und Digestauthentifizierung entspricht dem Dokument zur HTTP-Authentifizierung RCF 2617: „Basic and Digest Authentication“ (Einfache und Digestauthentifizierung), das auf der Website des [World Wide Web Consortium](https://www.w3.org) zum Download zur Verfügung steht.  
  
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
> Mittels Standard- und Hashwertauthentifizierung gesendete Daten sind nicht verschlüsselt und daher für Angreifer sichtbar. Anmeldeinformationen für die Standardauthentifizierung (Benutzername und Kennwort) werden zudem in Klartext gesendet und können abgefangen werden.  
  
## <a name="see-also"></a>Siehe auch

- [NTLM- und Kerberos-Authentifizierung](ntlm-and-kerberos-authentication.md)
- [Internet Authentication (Internetauthentifizierung)](internet-authentication.md)
