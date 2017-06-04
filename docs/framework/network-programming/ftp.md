---
title: "FTP | Microsoft Docs"
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
  - "FTP"
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# FTP
. .NET Framework stellt umfassende Unterstützung für das FTP\-Protokoll mit den <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse>\-Klassen.  Diese Klassen werden von <xref:System.Net.WebRequest> und von <xref:System.Net.WebResponse> abgeleitet.  In den meisten Fällen stellen <xref:System.Net.WebRequest> und die <xref:System.Net.WebResponse>\-Klassen alles, dass erforderlich ist, um die Anwendung zu stellen, aber, wenn Sie Zugriff auf FTP\-Besondere Funktionen benötigen, die als Eigenschaften verfügbar gemacht werden, können Sie diese verwendete Klassen zu <xref:System.Net.FtpWebRequest> oder zu <xref:System.Net.FtpWebResponse>.  
  
## Beispiele  
 Weitere Informationen finden Sie unter den folgenden Themen: [Gewusst wie: Herunterladen von Dateien über FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [Gewusst wie: Hochladen von Dateien über FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md) und [Gewusst wie: Auflisten von Verzeichnisinhalt mit FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).  
  
## FTP und Proxy  
 Wenn ein Proxy \(angegeben durch die <xref:System.Net.FtpWebRequest.Proxy%2A>\-Eigenschaft\) ein HTTP\-Proxy ist, kann nur <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> und <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> Befehle werden unterstützt.  
  
## Siehe auch  
 [Zugreifen auf das Internet über einen Proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)   
 [FTP\-Client\-Technologie\-Beispiel](http://go.microsoft.com/fwlink/?LinkID=179557)   
 [FTP\-Explorer\-Technologie\-Beispiel](http://go.microsoft.com/fwlink/?LinkID=179569)   
 [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)