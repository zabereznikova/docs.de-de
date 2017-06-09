---
title: "Standard- und Digestauthentifizierung | Microsoft Docs"
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
  - "Authentifizierung [.NET Framework], Klassen"
  - "Standardauthentifizierung."
  - "Authentifizierung [.NET Framework], Standard"
  - "Clientauthentifizierung, Standard"
  - "Benutzerauthentifizierung, Standard"
  - "Authentifizierung [.NET Framework], Digest"
  - "Empfangen von Daten, Authentifizierung"
  - "Clientauthentifizierung, Digest"
  - "Internet, Authentifizierung"
  - "Digestauthentifizierung"
  - "Senden von Daten, Authentifizierung"
  - "Netzwerkressourcen, Authentifizierung"
  - "Benutzerauthentifizierung, Digest"
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Standard- und Digestauthentifizierung
Die <xref:System.Net> Implementierung von grundlegendem und von Digestauthentifizierung stimmt mit RFC2617 \- HTTP\-Authentifizierung aus: Basis\- und Digestauthentifizierung \(verfügbar auf der Website des World Wide Web Consortium\) unter www.w3.org.  
  
 Um grundlegende und Digestauthentifizierung zu verwenden, muss eine Anwendung einen Benutzernamen und ein Kennwort in der <xref:System.Net.WebRequest.Credentials%2A>\-Eigenschaft des <xref:System.Net.WebRequest>\-Objekt bereitstellen, mit dem Daten aus dem Internet angefordert werden, wie im folgenden Beispiel gezeigt.  
  
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
>  Die Daten, die mit Basis\- und Digestauthentifizierung gesendet werden, werden nicht verschlüsselt, sodass die Daten von einem Angreifer angezeigt werden.  Außerdem werden Standardauthentifizierungsanmeldeinformationen \(Benutzername und Kennwort\) im Sie deaktivieren gesendet und können abgefangen werden.  
  
## Siehe auch  
 [NTLM\- und Kerberos\-Authentifizierung](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)   
 [Internetauthentifizierung](../../../docs/framework/network-programming/internet-authentication.md)