---
title: Eintragen von Ressourcen als Teilnehmer an einer Transaktion
description: Eintragen von Ressourcen als Teilnehmer in einer .NET-Transaktion. Jede Ressource in einer Transaktion wird von einem Ressourcen-Manager verwaltet, der von einem Transaktions-Manager koordiniert wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 786a12c2-d530-49f4-9c59-5c973e15a11d
ms.openlocfilehash: c3c777593750b3a4f05ae97ed6e26e19f58e4d72
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141874"
---
# <a name="enlisting-resources-as-participants-in-a-transaction"></a>Eintragen von Ressourcen als Teilnehmer an einer Transaktion

Jede an einer Transaktion teilnehmende Ressource wird von einem Ressourcen-Manager (RM) verwaltet, dessen Aktionen von einem Transaktions-Manager (TM) koordiniert werden. Die Koordination erfolgt anhand von Benachrichtigungen, die Abonnenten übermittelt werden, die sich über den TM in eine Transaktion eingetragen haben.

In diesem Thema wird beschrieben, wie eine oder mehrere Ressourcen in eine Transaktion eingetragen werden können. Zudem werden die verschiedenen Eintragungstypen erläutert. Im Thema [Commit a Transaction in Single-Phase and Multi-Phase](committing-a-transaction-in-single-phase-and-multi-phase.md) wird erläutert, wie die Transaktions Verpflichtung zwischen den eingetragenen Ressourcen koordiniert werden kann.

## <a name="enlisting-resources-in-a-transaction"></a>Eintragen von Ressourcen in eine Transaktion

Damit eine Ressource an einer Transaktion teilnehmen kann, muss sie sich in die Transaktion eintragen. Die- <xref:System.Transactions.Transaction> Klasse definiert einen Satz von Methoden, deren Namen mit **Enlist** beginnen, die diese Funktion bereitstellen. Die unterschiedlichen **Enlist** -Methoden entsprechen den unterschiedlichen Arten der Eintragung, die ein Ressourcen-Manager aufweisen kann. Die <xref:System.Transactions.Transaction.EnlistVolatile%2A>-Methoden werden für flüchtige Ressourcen und die <xref:System.Transactions.Transaction.EnlistDurable%2A>-Methode wird für dauerhafte Ressourcen verwendet. Die Dauerhaftigkeit (oder im Gegensatz dazu die Flüchtigkeit) eines Ressourcen-Managers leitet sich davon ab, ob der Ressourcen-Manager die Wiederherstellung nach einem Fehler unterstützt. Wenn ein RM die Wiederherstellung nach einem Fehler unterstützt, legt er Daten während Phase 1 (Vorbereitung) in einem permanenten Speicher ab, damit er sich im Falle eines Ausfalls nach der Wiederherstellung erneut in die Transaktion eintragen und entsprechend den Benachrichtigungen des TM geeignete Aktionen ausführen kann. Im Allgemeinen verwalten flüchtige RMs flüchtige Ressourcen wie beispielsweise eine speicherinterne Datenstruktur (z. B. eine speicherinterne Transaktions-Hashtabelle), und dauerhafte RMs verwalten Ressourcen, die über einen beständigeren Sicherungsspeicher verfügen (z. B. eine Datenbank, deren Sicherungsspeicher ein Datenträger ist).

Nachdem auf der Grundlage der Dauerhaftigkeit Ihrer Ressource entschieden wurde, ob die <xref:System.Transactions.Transaction.EnlistDurable%2A>-Methode oder die <xref:System.Transactions.Transaction.EnlistVolatile%2A>-Methode verwendet wird, sollten Sie Ihre Ressource für die Teilnahme an einem Zweiphasencommit (2PC) eintragen, indem Sie die <xref:System.Transactions.IEnlistmentNotification>-Schnittstelle für Ihren RM implementieren. Weitere Informationen zu 2PC finden Sie unter [Commit a Transaction in Single-Phase and Multi-Phase](committing-a-transaction-in-single-phase-and-multi-phase.md).

Ein einzelner Teilnehmer kann sich für mehrere dieser Protokolle eintragen, indem er <xref:System.Transactions.Transaction.EnlistDurable%2A> und <xref:System.Transactions.Transaction.EnlistVolatile%2A> mehrmals aufruft.

### <a name="durable-enlistment"></a>Dauerhafte Eintragung

Die <xref:System.Transactions.Transaction.EnlistDurable%2A>-Methoden werden verwendet, um einen RM zur Teilnahme an der Transaktion als dauerhafte Ressource einzutragen.  Wenn ein dauerhafter RM während einer Transaktion durch eine Unterbrechung ausfällt, wird erwartet, dass er eine Wiederherstellung durchführen kann, sobald er wieder online ist, indem er sich erneut (mithilfe der <xref:System.Transactions.TransactionManager.Reenlist%2A>-Methode) in alle Transaktionen einträgt, an denen er teilgenommen und für die er die Phase 2 nicht abgeschlossen hat. Nach Beendigung des Wiederherstellungsprozesses muss er zudem <xref:System.Transactions.TransactionManager.RecoveryComplete%2A> aufrufen. Weitere Informationen zur Wiederherstellung finden Sie unter [Durchführen der Wiederherstellung](performing-recovery.md).

Die <xref:System.Transactions.Transaction.EnlistDurable%2A>-Methoden nehmen alle ein <xref:System.Guid>-Objekt als ersten Parameter an. <xref:System.Guid> wird vom TM dazu verwendet, eine dauerhafte Eintragung einem bestimmten RM zuzuordnen. Daher ist es zwingend erforderlich, dass ein RM dieselbe <xref:System.Guid>-Identifikation verwendet (selbst bei einem Neustart mit mehreren RMs), da ansonsten die Wiederherstellung fehlschlagen kann.

Der zweite Parameter der <xref:System.Transactions.Transaction.EnlistDurable%2A>-Methode ist ein Verweis auf das Objekt, das der RM implementiert, um Transaktionsbenachrichtigungen zu erhalten. Die von Ihnen verwendete Überladung informiert den TM darüber, ob Ihr RM die Einphasencommit(SPC)-Optimierung unterstützt. Meist empfiehlt sich die Implementierung der <xref:System.Transactions.IEnlistmentNotification>-Schnittstelle, um an einem Zweiphasencommit (2PC) teilzunehmen. Wenn Sie den Commitvorgang jedoch optimieren möchten, können Sie die <xref:System.Transactions.ISinglePhaseNotification>-Schnittstelle für das Einphasencommit implementieren. Weitere Informationen zu SPC finden Sie unter Commit [a Transaction in Single-Phase and Multi-](committing-a-transaction-in-single-phase-and-multi-phase.md) Phase and [Optimization using Single Phase Commit and Promotable Single Phase Notification](optimization-spc-and-promotable-spn.md).

Der dritte Parameter ist eine <xref:System.Transactions.EnlistmentOptions>-Enumeration, deren Wert <xref:System.Transactions.EnlistmentOptions.None> oder <xref:System.Transactions.EnlistmentOptions.EnlistDuringPrepareRequired> sein kann. Wenn der Wert auf <xref:System.Transactions.EnlistmentOptions.EnlistDuringPrepareRequired> festgelegt ist, kann die Eintragung bei Erhalt der Vorbereitungsbenachrichtigung vom TM weitere RMs aufnehmen. Jedoch sollten Sie bedenken, dass für diesen Eintragungstyp keine Einphasencommit-Optimierung möglich ist.

### <a name="volatile-enlistment"></a>Flüchtige Eintragung

Teilnehmer, die flüchtige Ressourcen, wie z. B. einen Cache, verwalten, sollten sich mithilfe der <xref:System.Transactions.Transaction.EnlistVolatile%2A>-Methoden eintragen. Diese Objekte sind möglicherweise nicht in der Lage, nach einem Systemausfall das Ergebnis einer Transaktion zu empfangen oder den Status der Transaktion, an der sie teilnehmen, wiederherzustellen.

Wie zuvor bereits ausgeführt, nimmt ein RM eine flüchtige Eintragung vor, wenn er eine speicherinterne, flüchtige Ressource verwaltet. Einer der Vorteile der Verwendung von <xref:System.Transactions.Transaction.EnlistVolatile%2A> besteht darin, dass keine unnötige Eskalation der Transaktion erzwungen wird. Weitere Informationen zur Transaktions Eskalation finden Sie im Thema zur [Eskalation der Transaktions Verwaltung](transaction-management-escalation.md) . Das Eintragen von Schwankungen impliziert sowohl einen Unterschied bei der Verarbeitung der Eintragung durch den Transaktions-Manager als auch das, was vom Transaktions-Manager für den Ressourcen-Manager erwartet wird. Das liegt daran, dass ein flüchtiger Ressourcen-Manager keine Wiederherstellung durchführt. Die <xref:System.Transactions.Transaction.EnlistVolatile%2A>-Methoden verwenden den <xref:System.Guid>-Parameter nicht, weil ein flüchtiger Ressourcen-Manager keine Wiederherstellung durchführt und die <xref:System.Transactions.TransactionManager.Reenlist%2A>-Methode nicht aufruft, die <xref:System.Guid> benötigt.

Wie bei den dauerhaften Eintragungen erkennt der TM an der Überladungsmethode, die Sie zur Eintragung verwenden, ob Ihr RM die Einphasencommit-Optimierung unterstützt. Da ein flüchtiger Ressourcen-Manager keine Wiederherstellung durchführen kann, werden während der Vorbereitungsphase für eine flüchtige Eintragung keine Wiederherstellungsinformationen geschrieben. Daher führt der Aufruf der <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A>-Methode zu <xref:System.InvalidOperationException>.

Im folgenden Beispiel wird die Eintragung mithilfe der <xref:System.Transactions.Transaction.EnlistVolatile%2A>-Schnittstelle eines solchen Objekts als Teilnehmer in einer Transaktion veranschaulicht.

[!code-csharp[Tx_Enlist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#1)]
[!code-vb[Tx_Enlist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#1)]

### <a name="optimizing-performance"></a>Optimieren der Leistung

Die <xref:System.Transactions.Transaction>-Klasse stellt die <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>-Methode auch bereit, um eine Erweiterbare Einphaseneintragung (PSPE) vorzunehmen. Dadurch wird es einem dauerhaften RM ermöglicht, eine Transaktion zu hosten und zu "besitzen", die später bei Bedarf eskaliert werden kann, um von MSDTC verwaltet zu werden. Weitere Informationen hierzu finden [Sie unter Optimization using Single Phase Commit and Promotable Single Phase Notification](optimization-spc-and-promotable-spn.md).

## <a name="see-also"></a>Siehe auch

- [Optimierung mit Einphasencommit und Heraufstufbarer Einphasenbenachrichtigung](optimization-spc-and-promotable-spn.md)
- [Ausführen eines Einphasen- oder Mehrphasencommits für eine Transaktion](committing-a-transaction-in-single-phase-and-multi-phase.md)
