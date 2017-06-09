---
title: "Verwenden von Secure Sockets Layer | Microsoft Docs"
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
  - "Netzwerk"
  - "SSL"
  - "Secure Sockets Layer"
  - "Anfordern von Daten aus dem Internet, Secure Sockets Layer"
  - "Senden von Daten, Secure Sockets Layer"
  - "Netzwerkressourcen"
  - "Datenanforderungen, Secure Sockets Layer"
  - "Empfangen von Daten, Secure Sockets Layer"
  - "Internet, Secure Sockets Layer"
ms.assetid: 6e4289e6-d1b7-4e82-ab0d-e83e3b6063ed
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Verwenden von Secure Sockets Layer
Die <xref:System.Net>\-Klassen verwenden \(Secure Sockets Layer\) um die Verbindung für mehrere Netzwerkprotokolle zu verschlüsseln.  
  
 Für HTTP\-Verbindungen verwenden die <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse>\-Klassen SSL, um Internet\-Hosts zu sein, die SSL unterstützen.  Die Entscheidung, ob von SSL verwenden wird durch die <xref:System.Net.WebRequest>\-Klasse, auf Grundlage der URI erfüllt, das sie angegeben ist.  Wenn das URI mit "https beginnt: ", wird SSL verwendet; wenn der URI mit HTTP "beginnt: ", wird eine unverschlüsselte Verbindung verwendet.  
  
 Um SSL mit FTP \(File Transfer Protocol\) zu verwenden, legen Sie die <xref:System.Net.FtpWebRequest.EnableSsl>\-Eigenschaft fest, um vor dem Aufrufen von <xref:System.Net.FtpWebRequest.GetResponse> auszurichten.  Entsprechend SSL mit Zugriff auf einen SMTP\-Server \(Simple\) zu verwenden, legen Sie die <xref:System.Net.Mail.SmtpClient.EnableSsl>\-Eigenschaft fest, um vor dem Senden der E\-Mail auszurichten.  
  
 Die <xref:System.Net.Security.SslStream>\-Klasse stellt eine streambasierte Abstraktion für SSL bereit und bietet viele Möglichkeiten, den SSL\-Handshake zu konfigurieren.  
  
## Beispiel  
  
### Code  
  
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
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Verweise auf **System.Net**\-Namespace.  
  
## Siehe auch  
 [Sicherheit in der Netzwerkprogrammierung](../../../docs/framework/network-programming/security-in-network-programming.md)   
 [Netzwerkprogrammierung in .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Zertifikatauswahl und \-überprüfung](../../../docs/framework/network-programming/certificate-selection-and-validation.md)