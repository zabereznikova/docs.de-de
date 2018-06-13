---
title: Von System.Transactions bereitgestellte Funktionen
ms.date: 03/30/2017
ms.assetid: e458cef9-63b5-4401-b448-1536dcd9d9e5
ms.openlocfilehash: 6fc20f8249f37f69689fb3fc6b3144792badad3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365929"
---
# <a name="features-provided-by-systemtransactions"></a>Von System.Transactions bereitgestellte Funktionen
In diesem Abschnitt wird beschrieben, wie Sie anhand der Funktionen, die der <xref:System.Transactions>-Namespace bereitstellt, Ihre eigene Transaktionsanwendung und Ihren eigenen Ressourcen-Manager schreiben können. In diesem Abschnitt wird insbesondere darauf eingegangen, wie eine (lokale oder verteilte) Transaktion erstellt wird und ein oder mehrere Teilnehmer daran teilnehmen können.  
  
## <a name="overview-of-systemtransactions"></a>Übersicht über System.Transactions  
 Die Infrastruktur, die von den Klassen im <xref:System.Transactions>-Namespace bereitgestellt werden, erleichtern die Transaktionsprogrammierung und machen sie effizienter, da von SQL Server, ADO.NET, Message Queuing (MSMQ) und Microsoft Distributed Transaction Coordinator (MSDTC) gestartete Transaktionen unterstützt werden. Der <xref:System.Transactions>-Namespace bietet sowohl ein explizites Programmiermodell, das auf der <xref:System.Transactions.Transaction>-Klasse basiert, als auch ein implizites Programmiermodell, das die <xref:System.Transactions.TransactionScope>-Klasse verwendet, in der Transaktionen automatisch von der Infrastruktur verwaltet werden. Weitere Informationen zum Erstellen einer transaktionsanwendung mit diesen beiden Modellen finden Sie unter [Erstellen einer Transaktionsanwendung](../../../../docs/framework/data/transactions/writing-a-transactional-application.md).  
  
 Der <xref:System.Transactions>-Namespace stellt auch Typen zur Implementierung eines Ressourcen-Managers bereit. Mit einem Ressourcen-Manager werden dauerhafte oder flüchtige in einer Transaktion verwendete Daten verwaltet. Zusammen mit dem Transaktions-Manager gewährleistet der Ressourcen-Manager Unteilbarkeit und Isolation für die Anwendung. Der von der <xref:System.Transactions>-Infrastruktur bereitgestellte Transaktions-Manager unterstützt Transaktionen, die mehrere flüchtige Ressourcen oder eine einzelne dauerhafte Ressource umfassen. Weitere Informationen zum Implementieren eines Ressourcen-Managers finden Sie unter [Implementieren eines Ressourcen-Managers](../../../../docs/framework/data/transactions/implementing-a-resource-manager.md).  
  
 Der Transaktions-Manager eskaliert zudem lokale Transaktionen durch Koordination mit einem datenträgerbasierten Transaktions-Manager wie DTC transparent zu verteilten Transaktionen, wenn sich ein zusätzlicher dauerhafter Ressourcen-Manager bei der Transaktion einträgt. Es gibt zwei grundlegende Methoden, mit der <xref:System.Transactions>-Infrastruktur eine verbesserte Leistung zu erreichen.  
  
-   Dynamische Eskalation: Sie stellt sicher, dass die <xref:System.Transactions>-Infrastruktur nur MSDTC verwendet, wenn die Transaktion mehrere verteilte Ressourcen betrifft. Weitere Informationen zur dynamischen Eskalation finden Sie unter [Management Transaktionseskalation](../../../../docs/framework/data/transactions/transaction-management-escalation.md) Thema.  
  
-   Erweiterbare Eintragungen: Ermöglichen es einer Ressource (z.B. einer Datenbank), Eigentümer der Transaktion zu werden, wenn sie die einzige Entität ist, die an der Transaktion teilnimmt. Gegebenenfalls kann die <xref:System.Transactions>-Infrastruktur die Verwaltung der Transaktion zu einem späteren Zeitpunkt an MSDTC eskalieren. Auch dies reduziert die Zahl der Fälle, in denen MSDTC verwendet wird. Heraufstufbare Eintragungen werden ausführlich im Thema[Optimierung mit einzelnen Phase Commit und heraufstufbare Single Phase Notification](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md).  
  
 Der <xref:System.Transactions>-Namespace definiert drei Vertrauensebenen – AllowPartiallyTrustedCallers (APTCA), DistributedTransactionPermission (DTP) und volle Vertrauenswürdigkeit –, die den Zugriff auf die verfügbar gemachten Ressourcentypen einschränken. Weitere Informationen zu den verschiedenen Vertrauensebenen finden Sie [Sicherheit Vertrauensebenen in den Zugriff auf Ressourcen](../../../../docs/framework/data/transactions/security-trust-levels-in-accessing-resources.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
### <a name="writing-a-transactional-application"></a>Erstellen einer Transaktionsanwendung  
 Der <xref:System.Transactions>-Namespace stellt zwei Modelle zum Erstellen von Transaktionsanwendungen bereit. [Implementieren eine implizite Transaktion mithilfe der Transaktionsbereich](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) wird beschrieben, wie die <xref:System.Transactions> Namespace unterstützt die Erstellung impliziter Transaktionen, die mithilfe der <xref:System.Transactions.TransactionScope> Klasse.  
  
 [Implementieren eine explizite Transaktion mit CommittableTransaction](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md) wird beschrieben, wie die <xref:System.Transactions> Namespace unterstützt die Erstellung von expliziter Transaktionen, die mithilfe der <xref:System.Transactions.CommittableTransaction> Klasse.  
  
 Zusätzliche Themen Erstellen einer transaktionsanwendung, finden Sie unter [Erstellen einer Transaktionsanwendung](../../../../docs/framework/data/transactions/writing-a-transactional-application.md).  
  
### <a name="implementing-a-resource-manager"></a>Implementieren eines Ressourcen-Managers  
 Um ein Ressourcen-Manager, die einbezogen werden kann in einer Transaktion zu implementieren, finden Sie unter [Implementieren eines Ressourcen-Managers](../../../../docs/framework/data/transactions/implementing-a-resource-manager.md). In diesem Abschnitt werden das Eintragen einer Ressource, das Durchführen eines Transaktionscommit, die Wiederherstellung nach einem Fehler und Best Practices für die Optimierung behandelt.
