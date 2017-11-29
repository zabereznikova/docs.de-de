---
title: "Transaktionen und Parallelität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4e06f54ed27a555daa30f16f452cd03c8e188a0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="transactions-and-concurrency"></a>Transaktionen und Parallelität
Eine Transaktion besteht aus einem einzelnen Befehl oder einer Gruppe von Befehlen, die als Paket ausgeführt werden. Mit Transaktionen können Sie mehrere Operationen in einem Arbeitsschritt zusammenfassen. Wenn an einer Stelle in der Transaktion ein Fehler auftritt, kann für alle Updates ein Rollback zum Zustand vor der Transaktion ausgeführt werden.  
  
 Eine Transaktion muss zur Gewährleistung der Datenkonsistenz die folgenden vier Kriterien, die so genannten ACID-Kriterien, erfüllen: <legacyItalic>Atomicity</legacyItalic> (Atomarität), <legacyItalic>Consistency</legacyItalic> (Konsistenz), <legacyItalic>Isolation</legacyItalic> und <legacyItalic>Durability</legacyItalic> (Dauerhaftigkeit). Die meisten relationalen Datenbanksysteme (z. B. Microsoft SQL Server) unterstützen Transaktionen, indem sie für Update-, Einfüge- oder Löschvorgänge, die durch eine Clientanwendung ausgeführt werden, entsprechende Sperr-, Protokollierungs- und Transaktionsverwaltungsfunktionen bereitstellen.  
  
> [!NOTE]
>  Transaktionen, an denen mehrere Ressourcen beteiligt sind, können die Parallelität senken, wenn Sperren zu lang gehalten werden. Halten Sie Transaktionen daher so kurz wie möglich.  
  
 Wenn an einer Transaktion mehrere Tabellen in derselben Datenbank oder auf demselben Server beteiligt sind, bieten explizite Transaktionen in gespeicherten Prozeduren oft eine bessere Leistung. Transaktionen in gespeicherten SQL Server-Prozeduren können Sie mithilfe der Transact-SQL-Anweisungen `BEGIN TRANSACTION`, `COMMIT TRANSACTION` und `ROLLBACK TRANSACTION` erstellen. Weitere Informationen dazu finden Sie in der SQL Server-Onlinedokumentation.  
  
 Transaktionen, an denen verschiedene Ressourcen-Manager beteiligt sind, z. B. Transaktionen zwischen [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] und Oracle, erfordern eine verteilte Transaktion.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Lokale Transaktionen](../../../../docs/framework/data/adonet/local-transactions.md)  
 Zeigt, wie Transaktionen für eine Datenbank ausgeführt werden können.  
  
 [Verteilte Transaktionen](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 Beschreibt die Ausführung von verteilten Transaktionen in ADO.NET.  
  
 [System.Transactions-Integration in SQLServer](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 Beschreibt die <xref:System.Transactions>-Integration in [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] zum Arbeiten mit verteilten Transaktionen.  
  
 [Vollständige Parallelität](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 Beschreibt die vollständige und die eingeschränkte Parallelität und wie Sie auf Parallelitätsverletzungen testen können.  
  
## <a name="see-also"></a>Siehe auch  
 [Transaktionsgrundlagen](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 [Aufbauen der Verbindung zu einer Datenquelle](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 ["DataAdapters" und "DataReaders"](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
