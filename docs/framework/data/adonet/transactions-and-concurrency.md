---
title: Transaktionen und Parallelität
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: 049e402345e1abbb46739e48c89101207a43bb27
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191670"
---
# <a name="transactions-and-concurrency"></a>Transaktionen und Parallelität

Eine Transaktion besteht aus einem einzelnen Befehl oder einer Gruppe von Befehlen, die als Paket ausgeführt werden. Mit Transaktionen können Sie mehrere Operationen in einem Arbeitsschritt zusammenfassen. Wenn an einer Stelle in der Transaktion ein Fehler auftritt, kann für alle Updates ein Rollback zum Zustand vor der Transaktion ausgeführt werden.  
  
 Eine Transaktion muss zur Gewährleistung der Datenkonsistenz die folgenden vier Kriterien, die so genannten ACID-Kriterien, erfüllen: Atomicity (Atomarität), Consistency (Konsistenz), Isolation und Durability (Dauerhaftigkeit). Die meisten relationalen Datenbanksysteme (z. B. Microsoft SQL Server) unterstützen Transaktionen, indem sie für Update-, Einfüge- oder Löschvorgänge, die durch eine Clientanwendung ausgeführt werden, entsprechende Sperr-, Protokollierungs- und Transaktionsverwaltungsfunktionen bereitstellen.  
  
> [!NOTE]
> Transaktionen, an denen mehrere Ressourcen beteiligt sind, können die Parallelität senken, wenn Sperren zu lang gehalten werden. Halten Sie Transaktionen daher so kurz wie möglich.  
  
 Wenn an einer Transaktion mehrere Tabellen in derselben Datenbank oder auf demselben Server beteiligt sind, bieten explizite Transaktionen in gespeicherten Prozeduren oft eine bessere Leistung. Transaktionen in gespeicherten SQL Server-Prozeduren können Sie mithilfe der Transact-SQL-Anweisungen `BEGIN TRANSACTION`, `COMMIT TRANSACTION` und `ROLLBACK TRANSACTION` erstellen. Weitere Informationen finden Sie in der SQL Server-Onlinedokumentation.  
  
 Transaktionen, die verschiedene Ressourcen-Manager betreffen, wie z. b. eine Transaktion zwischen SQL Server und Oracle, erfordern eine verteilte Transaktion.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Lokale Transaktionen](local-transactions.md)  
 Zeigt, wie Transaktionen für eine Datenbank ausgeführt werden können.  
  
 [Distributed Transactions](distributed-transactions.md) (Verteilte Transaktionen)  
 Beschreibt die Ausführung von verteilten Transaktionen in ADO.NET.  
  
 [System.Transactions-Integration in SQL Server](system-transactions-integration-with-sql-server.md)  
 Beschreibt die <xref:System.Transactions> Integration in SQL Server zum Arbeiten mit verteilten Transaktionen.  
  
 [Optimistische Nebenläufigkeit](optimistic-concurrency.md)  
 Beschreibt die vollständige und die eingeschränkte Parallelität und wie Sie auf Parallelitätsverletzungen testen können.  
  
## <a name="see-also"></a>Weitere Informationen

- [Transaktionsgrundlagen](../transactions/transaction-fundamentals.md)
- [Herstellen der Verbindung mit einer Datenquelle](connecting-to-a-data-source.md)
- [Befehle und Parameter](commands-and-parameters.md)
- ["DataAdapters" und "DataReaders"](dataadapters-and-datareaders.md)
- [DbProviderFactories](dbproviderfactories.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
