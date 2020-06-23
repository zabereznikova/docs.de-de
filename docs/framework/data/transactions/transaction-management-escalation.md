---
title: Eskalation der Transaktionsverwaltung
description: Erfahren Sie mehr über die Eskalation der Transaktions Verwaltung in .net, bei der es sich um den Prozess der Migration einer Transaktion von den Komponenten eines Transaktions-Managers zu einem anderen handelt
ms.date: 03/30/2017
ms.assetid: 1e96331e-31b6-4272-bbbd-29ed1e110460
ms.openlocfilehash: a0b70f4be0f041be95b02537e06f9ec19a9b6183
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141656"
---
# <a name="transaction-management-escalation"></a>Eskalation der Transaktionsverwaltung
Windows umfasst eine Reihe von Diensten und Modulen, die zusammen einen Transaktions-Manager bilden. Unter der Eskalation der Transaktionsverwaltung wird die Übertragung einer Transaktion von einer Komponente zu einer anderen Komponente des Transaktions-Managers verstanden.  
  
 <xref:System.Transactions>beinhaltet eine Transaktions-Manager-Komponente, die eine Transaktion koordiniert, die höchstens eine einzelne dauerhafte Ressource oder mehrere flüchtige Ressourcen umfasst. Weil der Transaktions-Manager nur Aufrufe innerhalb der Anwendungsdomäne tätigt, erzielt er die optimale Leistung. Entwickler müssen nicht direkt mit dem Transaktions-Manager arbeiten. Stattdessen wird vom <xref:System.Transactions>-Namespace eine gemeinsame Infrastruktur bereitgestellt, die Schnittstellen, gemeinsames Verhalten und Hilfsklassen definiert.  
  
 Wenn Sie die Transaktion einem Objekt in einer anderen Anwendungsdomäne (einschließlich Prozess-und Computer Grenzen) auf demselben Computer bereitstellen möchten, eskaliert die- <xref:System.Transactions> Infrastruktur automatisch die Transaktion, die vom Microsoft Distributed Transaction Coordinator (MSDTC) verwaltet wird. Die Eskalation erfolgt auch dann, wenn Sie einen anderen permanenten Ressourcen-Manager eintragen. Nach der Eskalation wird die Transaktion bis zu ihrem Abschluss weiterhin in ihrem eskalierten Zustand verwaltet.  
  
 Zwischen der <xref:System.Transactions>-Transaktion und der MSDTC-Transaktion gibt es einen zwischengelagerten Transaktionstyp, der durch die PSPE (Promotable Single Phase Enlistment) zur Verfügung gestellt wird. PSPE ist ein weiterer wichtiger Mechanismus in <xref:System.Transactions>, der zur Leistungsoptimierung dient. Er ermöglicht es, dass sich eine einzelne dauerhafte Remoteressource, die sich in einer anderen Anwendungsdomäne, einem anderen Prozess oder auf einem anderen Computer befindet, an einer <xref:System.Transactions>-Transaktion beteiligt, ohne dass diese dadurch zu einer MSDTC-Transaktion eskaliert wird. Weitere Informationen zu PSPE finden Sie unter eintragen von [Ressourcen als Teilnehmer in einer Transaktion](enlisting-resources-as-participants-in-a-transaction.md).  
  
## <a name="how-escalation-is-initiated"></a>Wie die Eskalation initiiert wird  
 Die Transaktionseskalation mindert die Leistung, weil der MSDTC in einem eigenen Prozess ausgeführt wird und die Eskalation einer Transaktion an den MSDTC in einem Nachrichtenaustausch zwischen Prozessen resultiert. Um die Leistung zu verbessern, sollten Sie die Eskalation an MSDTC verzögern oder vermeiden, und daher müssen Sie wissen, wie und wann die Eskalation initiiert wird.  
  
 Solange die <xref:System.Transactions>-Infrastruktur flüchtige Ressourcen und höchstens eine dauerhafte Ressource verwaltet, die Einphasenbenachrichtigungen unterstützt, wird die Transaktion von der <xref:System.Transactions>-Infrastruktur verwaltet Der Transaktions-Manager wird nur denjenigen Ressourcen zur Verfügung gestellt, die sich in der gleichen Anwendungsdomäne befinden und für deren Protokollierung (Schreiben der Transaktionsergebnisse auf den Datenträger) keine Anmeldung erforderlich ist. Eine Eskalation, die bewirkt, dass die <xref:System.Transactions>-Infrastruktur die Verantwortung für die Transaktion dem MSDTC überträgt, tritt unter folgenden Bedingungen auf:  
  
- Mindestens eine dauerhafte Ressource, die keine Einphasenbenachrichtigungen unterstützt, ist in der Transaktion eingetragen.  
  
- Mindestens zwei permanente Ressourcen, die Einphasenbenachrichtigungen unterstützen, sind in der Transaktion eingetragen. Beispielsweise führt das Eintragen einer einzelnen Verbindung mit SQL Server 2005 nicht dazu, dass eine Transaktion höher gestuft wird. Wenn Sie jedoch eine zweite Verbindung mit einer SQL Server 2005-Datenbank öffnen, die dazu führt, dass die Datenbank eingetragen wird, <xref:System.Transactions> erkennt die Infrastruktur, dass es sich um die zweite dauerhafte Ressource in der Transaktion handelt, und eskaliert Sie in eine MSDTC-Transaktion.  
  
- Daraufhin wird eine Anforderung erzeugt, um die Transaktion an eine andere Anwendungsdomäne oder einen anderen Prozess zu "marshallen". Zum Beispiel die Serialisierung des Transaktionsobjekts über eine Anwendungsdomänengrenze hinweg. Das Transaktionsobjekt wird als Wert gemarshallt, und dies bedeutet, dass das Transaktionsobjekt serialisiert wird, sobald es über eine Anwendungsdomänengrenze (auch im gleichen Prozess) hinweg übergeben werden soll. Sie können Transaktionsobjekte übergeben, indem Sie eine Remotemethode aufrufen, die ein <xref:System.Transactions.Transaction>-Objekt als Parameter übernimmt, oder Sie können versuchen, auf eine Remotekomponente zuzugreifen, die von einer Transaktion bedient wird. Dadurch wird das Transaktionsobjekt serialisiert und genauso eskaliert, wie in dem Fall, in dem die Transaktion über eine Anwendungsdomäne hinweg serialisiert wird. Es wird verteilt, und der lokale Transaktions-Manager ist nicht mehr geeignet.  
  
 In der folgenden Tabelle werden alle möglichen Ausnahmen aufgelistet, die während der Eskalation ausgelöst werden können.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|Es wurde versucht, eine Transaktion mit einer Isolationsebene von <xref:System.Transactions.IsolationLevel.Snapshot> zu eskalieren.|  
|<xref:System.Transactions.TransactionAbortedException>|Der Transaktions-Manager ist nicht aktiv.|  
|<xref:System.Transactions.TransactionException>|Die Eskalation schlägt fehl, und die Anwendung wird abgebrochen.|
