---
title: NTLM- und Kerberos-Authentifizierung
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
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 36e88b163ab857180a02278828dba7dcec457736
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ntlm-and-kerberos-authentication"></a>NTLM- und Kerberos-Authentifizierung
Die NTLM- und Kerberos-Authentifizierung verwendet standardmäßig die mit der aufrufenden Anwendung verbundenen Benutzeranmeldeinformationen von Microsoft Windows NT, um sich bei einem Server zu authentifizieren. Bei der nicht standardmäßigen NTLM-Authentifizierung wird der Authentifizierungstyp durch die Anwendung auf NTLM festgelegt. Mithilfe des <xref:System.Net.NetworkCredential>-Objekts wird, wie im folgenden Beispiel gezeigt, der Benutzername, das Kennwort und die Domäne an den Host übergeben.  
  
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
  
 Anwendungen, die sich mit den Anmeldeinformationen des Anwendungsbenutzers mit Internetdiensten verbinden müssen, können wie im folgenden Beispiel gezeigt über die Standardanmeldeinformationen des Benutzers verbunden werden.  
  
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
  
 Mithilfe des Negotiate-Authentifizierungsmoduls wird bestimmt, ob der Remoteserver die NTLM- oder Kerberos-Authentifizierung verwendet, und es wird die entsprechende Antwort gesendet.  
  
> [!NOTE]
>  Die NTLM-Authentifizierung funktioniert nicht über einen Proxyserver.  
  
## <a name="see-also"></a>Siehe auch  
 [Grundlegende und Digestauthentifizierung](../../../docs/framework/network-programming/basic-and-digest-authentication.md)  
 [Internet Authentication (Internetauthentifizierung)](../../../docs/framework/network-programming/internet-authentication.md)
