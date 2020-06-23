---
title: Von System.Transactions bereitgestellte Funktionen
description: Überprüfen Sie die Funktionen, die vom System. Transactions-Namespace in .NET bereitgestellt werden, um Ihre eigene Transaktions Anwendung und den Ressourcen-Manager zu schreiben.
ms.date: 03/30/2017
ms.assetid: e458cef9-63b5-4401-b448-1536dcd9d9e5
ms.openlocfilehash: 0278e9248305572c6156c6500f1fe51a8b3f3338
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141861"
---
# <a name="features-provided-by-systemtransactions"></a>Von System.Transactions bereitgestellte Funktionen
In diesem Abschnitt wird beschrieben, wie Sie anhand der Funktionen, die der <xref:System.Transactions>-Namespace bereitstellt, Ihre eigene Transaktionsanwendung und Ihren eigenen Ressourcen-Manager schreiben können. In diesem Abschnitt wird insbesondere darauf eingegangen, wie eine (lokale oder verteilte) Transaktion erstellt wird und ein oder mehrere Teilnehmer daran teilnehmen können.  
  
## <a name="overview-of-systemtransactions"></a>Übersicht über System.Transactions  
 Die Infrastruktur, die von den Klassen im <xref:System.Transactions>-Namespace bereitgestellt werden, erleichtern die Transaktionsprogrammierung und machen sie effizienter, da von SQL Server, ADO.NET, Message Queuing (MSMQ) und Microsoft Distributed Transaction Coordinator (MSDTC) gestartete Transaktionen unterstützt werden. Der <xref:System.Transactions>-Namespace bietet sowohl ein explizites Programmiermodell, das auf der <xref:System.Transactions.Transaction>-Klasse basiert, als auch ein implizites Programmiermodell, das die <xref:System.Transactions.TransactionScope>-Klasse verwendet, in der Transaktionen automatisch von der Infrastruktur verwaltet werden. Weitere Informationen zum Erstellen einer Transaktions Anwendung mit diesen beiden Modellen finden Sie unter [Schreiben einer transaktionalen Anwendung](writing-a-transactional-application.md).  
  
 Der <xref:System.Transactions>-Namespace stellt auch Typen zur Implementierung eines Ressourcen-Managers bereit. Mit einem Ressourcen-Manager werden dauerhafte oder flüchtige in einer Transaktion verwendete Daten verwaltet. Zusammen mit dem Transaktions-Manager gewährleistet der Ressourcen-Manager Unteilbarkeit und Isolation für die Anwendung. Der von der <xref:System.Transactions>-Infrastruktur bereitgestellte Transaktions-Manager unterstützt Transaktionen, die mehrere flüchtige Ressourcen oder eine einzelne dauerhafte Ressource umfassen. Weitere Informationen zum Implementieren eines Ressourcen-Managers finden Sie unter [Implementieren einer Ressourcen-Manager](implementing-a-resource-manager.md).  
  
 Der Transaktions-Manager eskaliert zudem lokale Transaktionen durch Koordination mit einem datenträgerbasierten Transaktions-Manager wie DTC transparent zu verteilten Transaktionen, wenn sich ein zusätzlicher dauerhafter Ressourcen-Manager bei der Transaktion einträgt. Es gibt zwei grundlegende Methoden, mit der <xref:System.Transactions>-Infrastruktur eine verbesserte Leistung zu erreichen.  
  
- Dynamische Eskalation: Sie stellt sicher, dass die <xref:System.Transactions>-Infrastruktur nur MSDTC verwendet, wenn die Transaktion mehrere verteilte Ressourcen betrifft. Weitere Informationen zur dynamischen Eskalation siehe [Transaction Management Eskalations](transaction-management-escalation.md) Thema.  
  
- Erweiterbare Eintragungen: Ermöglichen es einer Ressource (z.B. einer Datenbank), Eigentümer der Transaktion zu werden, wenn sie die einzige Entität ist, die an der Transaktion teilnimmt. Gegebenenfalls kann die <xref:System.Transactions>-Infrastruktur die Verwaltung der Transaktion zu einem späteren Zeitpunkt an MSDTC eskalieren. Auch dies reduziert die Zahl der Fälle, in denen MSDTC verwendet wird. Heraufstufbare Eintragung werden ausführlich im Thema[Optimierung mithilfe eines einphasigen Commit und einer heraufstufbaren Einphasenbenachrichtigung](optimization-spc-and-promotable-spn.md)behandelt.  
  
 Der <xref:System.Transactions>-Namespace definiert drei Vertrauensebenen – AllowPartiallyTrustedCallers (APTCA), DistributedTransactionPermission (DTP) und volle Vertrauenswürdigkeit –, die den Zugriff auf die verfügbar gemachten Ressourcentypen einschränken. Weitere Informationen zu den verschiedenen Vertrauens Ebenen finden Sie unter [Sicherheits Vertrauensstellungen beim Zugriff auf Ressourcen](security-trust-levels-in-accessing-resources.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
### <a name="writing-a-transactional-application"></a>Erstellen einer Transaktionsanwendung  
 Der <xref:System.Transactions>-Namespace stellt zwei Modelle zum Erstellen von Transaktionsanwendungen bereit. [Durch das Implementieren einer impliziten Transaktion mit Transaktions Bereich](implementing-an-implicit-transaction-using-transaction-scope.md) wird beschrieben, wie der <xref:System.Transactions> Namespace das Erstellen impliziter Transaktionen mithilfe der-Klasse unterstützt <xref:System.Transactions.TransactionScope>  
  
 [Durch das Implementieren einer expliziten Transaktion mit CommittableTransaction](implementing-an-explicit-transaction-using-committabletransaction.md) wird beschrieben, wie das <xref:System.Transactions> Erstellen expliziter Transaktionen mithilfe der-Klasse vom-Namespace <xref:System.Transactions.CommittableTransaction>  
  
 Weitere Themen zum Schreiben einer Transaktions Anwendung finden Sie unter [Schreiben einer transaktionalen](writing-a-transactional-application.md)Anwendung.  
  
### <a name="implementing-a-resource-manager"></a>Implementieren eines Ressourcen-Managers  
 Informationen zum Implementieren eines Ressourcen-Managers, der an einer Transaktion teilnehmen kann, finden Sie unter [Implementieren einer Ressourcen-Manager](implementing-a-resource-manager.md). In diesem Abschnitt werden das Eintragen einer Ressource, das Durchführen eines Transaktionscommit, die Wiederherstellung nach einem Fehler und Best Practices für die Optimierung behandelt.
