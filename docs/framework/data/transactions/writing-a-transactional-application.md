---
title: Erstellen einer Transaktionsanwendung
description: Schreiben Sie eine transaktionale Anwendung in .net. Verwenden Sie ein explizites oder implizites Programmiermodell mit der Transaction-Klasse bzw. der transaktionscope-Klasse.
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: 0235bb507d974e0bd3a7046ea213d8b78d870d59
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415770"
---
# <a name="writing-a-transactional-application"></a>Erstellen einer Transaktionsanwendung
Als Programmierer von Transaktionsanwendungen können Sie die beiden Programmiermodelle nutzen, die der <xref:System.Transactions>-Namespace zum Erstellen von Transaktionen zur Verfügung stellt. Mithilfe der-Klasse können Sie das explizite Programmiermodell verwenden, indem Sie die- <xref:System.Transactions.Transaction> Klasse oder das implizite Programmiermodell verwenden, in dem Transaktionen automatisch von der-Infrastruktur verwaltet werden <xref:System.Transactions.TransactionScope> . Es wird empfohlen, dass Sie das implizite Transaktionsmodell für die Entwicklung verwenden. Weitere Informationen zur Verwendung eines Transaktions Bereichs finden Sie im Thema [Implementieren einer impliziten Transaktion mit Transaktions Bereich](implementing-an-implicit-transaction-using-transaction-scope.md) .  
  
 Beide Modelle unterstützen die Ausführung eines Commits für eine Transaktion, wenn das Programm einen konsistenten Zustand erreicht. Wenn der Commitvorgang erfolgreich ausgeführt wurde, ist die Transaktion abgeschlossen. Wenn der Commitvorgang fehlschlägt, wird die Transaktion abgebrochen. Wenn das Anwendungsprogramm die Transaktion nicht erfolgreich abschließen kann, versucht es, die Transaktion abzubrechen und deren Auswirkungen rückgängig zu machen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
### <a name="creating-a-transaction"></a>Erstellen einer Transaktion  
 Der <xref:System.Transactions>-Namespace stellt zwei Modelle zum Erstellen einer Transaktion bereit. Diese Modelle werden in den folgenden Themen behandelt.  
  
 [Implementieren einer impliziten Transaktion mit Transaktionsbereich](implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Hier wird beschrieben, wie der <xref:System.Transactions>-Namespace die Erstellung impliziter Transaktionen mithilfe der <xref:System.Transactions.TransactionScope>-Klasse unterstützt.  
  
 [Implementieren einer expliziten Transaktion mit CommittableTransaction](implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Hier wird beschrieben, wie der <xref:System.Transactions>-Namespace die Erstellung expliziter Transaktionen mithilfe der <xref:System.Transactions.CommittableTransaction>-Klasse unterstützt.  
  
### <a name="escalating-transaction-management"></a>Eskalieren der Transaktionsverwaltung  
 Wenn eine Transaktion auf eine Ressource aus einer anderen Anwendungsdomäne zugreifen muss oder wenn Sie einen anderen stabilen Ressourcen-Manager eintragen möchten, wird die Verwaltung der Transaktion automatisch MSDTC übertragen. Die Transaktions Eskalation wird im Thema [Transaction Management Eskalations](transaction-management-escalation.md) behandelt.  
  
### <a name="concurrency"></a>Parallelität  
 Das Thema Verwalten von Parallelität [mit DependentTransaction](managing-concurrency-with-dependenttransaction.md) veranschaulicht, wie die Parallelität zwischen asynchronen Aufgaben mithilfe der-Klasse erreicht werden kann <xref:System.Transactions.DependentTransaction> .  
  
### <a name="com-interop"></a>COM+-Interop  
 Das Thema [Interoperabilität mit Enterprise Services und com+-Transaktionen](interoperability-with-enterprise-services-and-com-transactions.md) veranschaulicht, wie Sie Ihre verteilten Transaktionen mit com+-Transaktionen interagieren können.  
  
### <a name="diagnostics"></a>Diagnose  
 [Diagnose](diagnostic-traces.md) Ablauf Verfolgungen beschreiben, wie Sie die von der-Infrastruktur generierten Ablauf Verfolgungs Codes verwenden können <xref:System.Transactions> , um Fehler in Ihren Anwendungen zu beheben.  
  
### <a name="working-within-aspnet"></a>Arbeiten in ASP.NET  
 Im Thema [using System. Transactions in ASP.net](using-system-transactions-in-aspnet.md) wird beschrieben, wie Sie <xref:System.Transactions> innerhalb einer ASP.NET-Anwendung erfolgreich verwenden können.
