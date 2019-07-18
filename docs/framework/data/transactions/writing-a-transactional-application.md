---
title: Erstellen einer Transaktionsanwendung
ms.date: 03/30/2017
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
ms.openlocfilehash: 048df434ff0ada2ab5f8c7473913f6c34c05d1a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793490"
---
# <a name="writing-a-transactional-application"></a>Erstellen einer Transaktionsanwendung
Als Programmierer von Transaktionsanwendungen können Sie die beiden Programmiermodelle nutzen, die der <xref:System.Transactions>-Namespace zum Erstellen von Transaktionen zur Verfügung stellt. Sie können das explizite Programmiermodell nutzen, mit der <xref:System.Transactions.Transaction> Klasse oder das implizite programmmiermodell, in dem Transaktionen werden automatisch von der Infrastruktur verwaltet, mit, der <xref:System.Transactions.TransactionScope> Klasse. Es wird empfohlen, dass Sie das implizite Transaktionsmodell für die Entwicklung verwenden. Sie finden weitere Informationen zur Verwendung ein Transaktionsbereichs, in der [Implementieren einer impliziten Transaktion mit Transaktionsbereich](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) Thema.  
  
 Beide Modelle unterstützen die Ausführung eines Commits für eine Transaktion, wenn das Programm einen konsistenten Zustand erreicht. Wenn der Commitvorgang erfolgreich ausgeführt wurde, ist die Transaktion abgeschlossen. Wenn der Commitvorgang fehlschlägt, wird die Transaktion abgebrochen. Wenn das Anwendungsprogramm die Transaktion nicht erfolgreich abschließen kann, versucht es, die Transaktion abzubrechen und deren Auswirkungen rückgängig zu machen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
### <a name="creating-a-transaction"></a>Erstellen einer Transaktion  
 Der <xref:System.Transactions>-Namespace stellt zwei Modelle zum Erstellen einer Transaktion bereit. Diese Modelle werden in den folgenden Themen behandelt.  
  
 [Implementieren einer impliziten Transaktion mit einem Transaktionsbereich](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Hier wird beschrieben, wie der <xref:System.Transactions>-Namespace die Erstellung impliziter Transaktionen mithilfe der <xref:System.Transactions.TransactionScope>-Klasse unterstützt.  
  
 [Implementieren einer expliziten Transaktion mit CommittableTransaction](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Hier wird beschrieben, wie der <xref:System.Transactions>-Namespace die Erstellung expliziter Transaktionen mithilfe der <xref:System.Transactions.CommittableTransaction>-Klasse unterstützt.  
  
### <a name="escalating-transaction-management"></a>Eskalieren der Transaktionsverwaltung  
 Wenn eine Transaktion auf eine Ressource aus einer anderen Anwendungsdomäne zugreifen muss oder wenn Sie einen anderen stabilen Ressourcen-Manager eintragen möchten, wird die Verwaltung der Transaktion automatisch MSDTC übertragen. Transaktionseskalation wird der [Eskalation der Transaktionsverwaltung](../../../../docs/framework/data/transactions/transaction-management-escalation.md) Thema.  
  
### <a name="concurrency"></a>Parallelität  
 Das Thema [Verwalten von Parallelität mit DependentTransaction](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md) wird veranschaulicht, wie Parallelität zwischen asynchronen Aufgaben mit erreicht werden kann die <xref:System.Transactions.DependentTransaction> Klasse.  
  
### <a name="com-interop"></a>COM+-Interop  
 Das Thema [Interoperabilität mit Enterprise Services und COM+-Transaktionen](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md) veranschaulicht, wie Sie Ihre verteilten Transaktionen mit COM+-Transaktionen interagieren vornehmen können.  
  
### <a name="diagnostics"></a>Diagnose  
 [Ablaufverfolgungen zur Diagnose](../../../../docs/framework/data/transactions/diagnostic-traces.md) wird beschrieben, wie Sie die ablaufverfolgungscodes verwenden können, die vom generierten der <xref:System.Transactions> Infrastruktur zur Problembehandlung von Fehlern in Ihren Anwendungen.  
  
### <a name="working-within-aspnet"></a>Arbeiten in ASP.NET  
 Die [Using System.Transactions in ASP.NET](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md) Thema wird beschrieben, wie Sie erfolgreich <xref:System.Transactions> innerhalb einer ASP.NET-Anwendung.
