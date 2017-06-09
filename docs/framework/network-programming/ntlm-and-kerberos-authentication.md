---
title: "NTLM- und Kerberos-Authentifizierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Authentifizierung [.NET Framework], NTLM"
  - "Authentifizierung [.NET Framework], Kerberos"
  - "Benutzerauthentifizierung, Kerberos"
  - "Benutzerauthentifizierung, NTLM"
  - "Kerberos-Authentifizierung"
  - "Empfangen von Daten, Authentifizierung"
  - "NTLM-Authentifizierung"
  - "Internet, Authentifizierung"
  - "Client-Authentifizierung, Kerberos"
  - "Senden von Daten, Authentifizierung"
  - "Netzwerkressourcen, Authentifizierung"
  - "Klassen [.NET Framework], Authentifizierung"
  - "Clientauthentifizierung, NTLM"
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# NTLM- und Kerberos-Authentifizierung
Standard NTLM\-Authentifizierung und Kerberos\-Authentifizierung verwenden die Microsoft Windows NT\-Benutzeranmeldeinformationen, die mit dem aufrufenden Anwendung zugeordnet werden, um Authentifizierung mit dem Server zu versuchen.  Wenn sie nicht standardmäßige NTLM\-Authentifizierung verwendet, legt die Anwendung den Authentifizierungstyp zu NTLM fest und verwendet ein <xref:System.Net.NetworkCredential>\-Objekt, um den Benutzernamen, das Kennwort und die Domäne an den Host, wie im folgenden Beispiel gezeigt zu übergeben.  
  
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
  
 Anwendungen, die auf Internetdienste unter Verwendung der Anmeldeinformationen des Anwendungsbenutzers herstellen müssen, können mit den standardmäßigen Anmeldeinformationen des Benutzers, wie im folgenden Beispiel gezeigt durchführen.  
  
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
  
 Das Negotiate\-Authentifizierungs\-Modul, bestimmt, ob der Remoteserver NTLM\- oder Kerberos\-Authentifizierung verwendet, und sendet die entsprechende Antwort.  
  
> [!NOTE]
>  NTLM\-Authentifizierung funktioniert nicht über einen Proxyserver.  
  
## Siehe auch  
 [Standard\- und Digestauthentifizierung](../../../docs/framework/network-programming/basic-and-digest-authentication.md)   
 [Internetauthentifizierung](../../../docs/framework/network-programming/internet-authentication.md)