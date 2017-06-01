---
title: "Die Kontextverbindung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Die Kontextverbindung
Das Problem des internen Datenzugriffs ist ein gängiges Szenario.  Dabei möchten Sie auf denselben Server zugreifen, auf dem die gespeicherte CLR\-Prozedur oder CLR\-Funktion \(Common Language Runtime\) ausgeführt wird.  Eine Option liegt darin, mithilfe von <xref:System.Data.SqlClient.SqlConnection> eine Verbindung zu erstellen, eine Verbindungszeichenfolge anzugeben, die auf den lokalen Server zeigt, und die Verbindung zu öffnen.  Dabei müssen Anmeldeinformationen für die Anmeldung angegeben werden.  Die Verbindung befindet sich in einer anderen Datenbanksitzung als die gespeicherte Prozedur oder Funktion, sie kann über andere `SET`\-Optionen verfügen, sie gehört zu einer separaten Transaktion, verfügt nicht über die temporären Tabellen usw.  Wenn der verwaltete gespeicherte Prozedur\- oder Funktionscode im SQL Server\-Prozess ausgeführt wird, liegt dies daran, dass eine Verbindung mit diesem Server hergestellt und eine SQL\-Anweisung ausgeführt wurde, die den Code aufruft.  Möglicherweise möchten Sie die gespeicherte Prozedur oder Funktion im Kontext dieser Verbindung ausführen, zusammen mit ihrer Transaktion, den `SET`\-Optionen usw.  Dies wird als Kontextverbindung bezeichnet.  
  
 Mit der Kontextverbindung können Sie Transact\-SQL\-Anweisungen in demselben Kontext ausführen, der für den Code beim ersten Aufruf galt.  Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server\-Onlinedokumentation**  
  
1.  [Kontextverbindungen](http://go.microsoft.com/fwlink/?LinkId=115395)  
  
## Siehe auch  
 [Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/de-de/5358a825-e19b-49aa-8214-674ce5fed1da)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)