---
title: "Gespeicherte CLR-Prozeduren | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Gespeicherte CLR-Prozeduren
Gespeicherte Prozeduren sind Routinen, die nicht in skalaren Ausdrücken verwendet werden können.  Sie können tabellarische Ergebnisse und Meldungen an den Client zurückgeben, DDL\-Anweisungen \(Data Definition Language – Datendefinitionssprache\) und DML\-Anweisungen \(Data Manipulation Language – Datenbearbeitungssprache\) aufrufen und Ausgabeparameter zurückgeben.  
  
> [!NOTE]
>  Microsoft Visual Basic unterstützt Ausgabeparameter nicht in derselben Weise wie Microsoft Visual C\#.  Sie müssen wie im Folgenden gezeigt angeben, dass der Parameter als Verweis übergeben werden soll, und das \<Out\(\)\>\-Attribut so anwenden, dass es einen Ausgabeparameter darstellt.  
  
```  
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```  
  
 Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server\-Onlinedokumentation**  
  
1.  [Gespeicherte CLR\-Prozeduren](http://go.microsoft.com/fwlink/?LinkId=115400)  
  
## Siehe auch  
 [Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/de-de/5358a825-e19b-49aa-8214-674ce5fed1da)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)