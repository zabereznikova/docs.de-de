---
title: "Transaktionen und Parallelit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Transaktionen und Parallelit&#228;t
Eine Transaktion besteht aus einem einzelnen Befehl oder einer Gruppe von Befehlen, die als Paket ausgeführt werden.  Mit Transaktionen können Sie mehrere Operationen in einem Arbeitsschritt zusammenfassen.  Wenn an einer Stelle in der Transaktion ein Fehler auftritt, kann für alle Updates ein Rollback zum Zustand vor der Transaktion ausgeführt werden.  
  
 Eine Transaktion muss zur Gewährleistung der Datenkonsistenz die folgenden vier Kriterien, die so genannten ACID\-Kriterien, erfüllen: \<legacyItalic\>Atomicity\<\/legacyItalic\> \(Atomarität\), \<legacyItalic\>Consistency\<\/legacyItalic\> \(Konsistenz\), \<legacyItalic\>Isolation\<\/legacyItalic\> und \<legacyItalic\>Durability\<\/legacyItalic\> \(Dauerhaftigkeit\).  Die meisten relationalen Datenbanksysteme \(z. B. Microsoft SQL Server\) unterstützen Transaktionen, indem sie für Update\-, Einfüge\- oder Löschvorgänge, die durch eine Clientanwendung ausgeführt werden, entsprechende Sperr\-, Protokollierungs\- und Transaktionsverwaltungsfunktionen bereitstellen.  
  
> [!NOTE]
>  Transaktionen, an denen mehrere Ressourcen beteiligt sind, können die Parallelität senken, wenn Sperren zu lang gehalten werden.  Halten Sie Transaktionen daher so kurz wie möglich.  
  
 Wenn an einer Transaktion mehrere Tabellen in derselben Datenbank oder auf demselben Server beteiligt sind, bieten explizite Transaktionen in gespeicherten Prozeduren oft eine bessere Leistung.  Transaktionen in gespeicherten SQL Server\-Prozeduren können Sie mithilfe der Transact\-SQL\-Anweisungen `BEGIN TRANSACTION`, `COMMIT TRANSACTION` und `ROLLBACK TRANSACTION` erstellen.  Weitere Informationen dazu finden Sie in der SQL Server\-Onlinedokumentation.  
  
 Transaktionen, an denen verschiedene Ressourcen\-Manager beteiligt sind, z. B. Transaktionen zwischen [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] und Oracle, erfordern eine verteilte Transaktion.  
  
## In diesem Abschnitt  
 [Lokale Transaktionen](../../../../docs/framework/data/adonet/local-transactions.md)  
 Zeigt, wie Transaktionen für eine Datenbank ausgeführt werden können.  
  
 [Verteilte Transaktionen](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 Beschreibt die Ausführung von verteilten Transaktionen in ADO.NET.  
  
 [System.Transactions\-Integration in SQL Server](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 Beschreibt die <xref:System.Transactions>\-Integration in [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] zum Arbeiten mit verteilten Transaktionen.  
  
 [Vollständige Parallelität](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 Beschreibt die vollständige und die eingeschränkte Parallelität und wie Sie auf Parallelitätsverletzungen testen können.  
  
## Siehe auch  
 [Transaction Fundamentals](http://msdn.microsoft.com/de-de/2a476b63-b94f-443f-992d-53943fdf4e5d)   
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)   
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [DataAdapter und DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 ['DbProviderFactory'](../../../../docs/framework/data/adonet/dbproviderfactories.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)