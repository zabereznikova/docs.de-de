---
title: Optimierung mit Einphasencommit und Heraufstufbarer Einphasenbenachrichtigung
description: Optimieren Sie die Leistung mithilfe eines einphasigen Commit und einer erweiterbaren Einphasenbenachrichtigung. Erfahren Sie mehr über die System. Transactions-Infrastruktur in .net.
ms.date: 03/30/2017
ms.assetid: 57beaf1a-fb4d-441a-ab1d-bc0c14ce7899
ms.openlocfilehash: 89ce82e673340c93254983c078f78a2501129383
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141977"
---
# <a name="optimization-using-single-phase-commit-and-promotable-single-phase-notification"></a>Optimierung mit Einphasencommit und Heraufstufbarer Einphasenbenachrichtigung

In diesem Thema wird der Mechanismus beschrieben, der von der <xref:System.Transactions>-Infrastruktur zur Leistungsoptimierung bereitgestellt wird.

## <a name="promotable-single-phase-enlistment"></a>Heraufstufbare Einphaseneintragung (PSPE)

Die <xref:System.Transactions>-Infrastruktur verwaltet eine Transaktion innerhalb einer einzelnen Anwendungsdomäne, die höchstens eine dauerhafte Ressource oder mehrere flüchtige Ressourcen umfasst. Da die <xref:System.Transactions>-Infrastruktur nur Domänenaufrufe innerhalb von Anwendungen verwendet, bietet sie den besten Durchsatz und die beste Leistung.

Wenn die Transaktion jedoch einem anderen Objekt in einer anderen Anwendungsdomäne (darunter fallen auch diejenigen, die prozess- und geräteübergreifend sind) auf demselben Computer bereitgestellt wird oder Sie einen anderen Manager für dauerhafte Ressourcen eintragen, eskaliert die <xref:System.Transactions>-Infrastruktur automatisch die Transaktion, die von MS DTC verwaltet werden soll. Eine vom MSDTC verwaltete Transaktion ist nicht so leistungsfähig wie eine von der <xref:System.Transactions>-Infrastruktur verwaltete.

Um die Leistung zu optimieren, stellt die <xref:System.Transactions>-Infrastruktur die Erweiterbare Einphaseneintragung (Promotable Single Phase Enlistment, PSPE) bereit, die es einer einzelnen dauerhaften Remote-Ressource in einer anderen Anwendungsdomäne, einem anderen Prozess oder auf einem anderen Gerät ermöglicht, an einer <xref:System.Transactions>-Transaktion teilzunehmen, ohne dass sie dadurch zu einer MSDTC-Transaktion eskaliert wird. Dieser Ressourcen-Manager (RM) kann eine Transaktion hosten und "besitzen", die später bei Bedarf zu einer verteilten Transaktion (oder einer MSDTC-Transaktion) eskaliert werden kann. Dies reduziert die Wahrscheinlichkeit, dass der MSDTC verwendet wird.

Dieser spezielle Ressourcen-Manager verfügt gewöhnlich über eigene interne, nicht verteilte Transaktionen und muss die Konvertierung dieser Transaktionen in verteilte Transaktionen zur Laufzeit unterstützen. SQL Server 2005 ist beispielsweise so ein Ressourcen-Manager. In diesem Fall übernimmt die <xref:System.Transactions>-Infrastruktur eine passive Verwaltungsrolle, indem sie lediglich überwacht, ob die Transaktion eskaliert werden muss. Damit die Interaktion zwischen der <xref:System.Transactions>-Infrastruktur und dem Ressourcen-Manager unterstützt wird, muss der Ressourcen-Manager die Schnittstelle <xref:System.Transactions.IPromotableSinglePhaseNotification> implementieren.

Die <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>-Methode wird verwendet, um eine einzelne dauerhafte Ressource einzutragen, die später eskaliert werden kann. Diese Methode stellt sicher, dass die Eintragung nach Bedarf eskaliert werden kann. Wenn die Eintragung erfolgreich ist, erstellt der RM seine interne Transaktion und ordnet sie der <xref:System.Transactions>-Transaktion zu. Wenn die PSPE-Eintragung fehlschlägt, sollte der RM die Eintragung stattdessen mit der <xref:System.Transactions.Transaction.EnlistDurable%2A>-Methode vornehmen. Zum Fehlschlagen der Eintragung in PSPE kann es kommen, wenn die Transaktion bereits verteilt ist oder ein anderer RM bereits eine PSPE-Eintragung vorgenommen hat.

Sobald die Eintragung erfolgt ist, werden Clientaufrufe zum Commit oder Abbruch der <xref:System.Transactions>-Transaktion in Aufrufe an den Ressourcen-Manager konvertiert, indem die <xref:System.Transactions.IPromotableSinglePhaseNotification.SinglePhaseCommit%2A>-Methode bzw. die <xref:System.Transactions.IPromotableSinglePhaseNotification.Rollback%2A>-Methode aufgerufen wird.

Wenn die <xref:System.Transactions>-Transaktion zu keinem Zeitpunkt eine Eskalation erfordert, erhält der RM eine <xref:System.Transactions.IPromotableSinglePhaseNotification.SinglePhaseCommit%2A>-Benachrichtigung, sobald ein Commit für die Transaktion ausgeführt wird. Er kann dann einen Commit für die interne Transaktion ausführen, die anfänglich erstellt wurde.

Wenn die <xref:System.Transactions>-Transaktion eskaliert werden muss (beispielsweise, um mehrere RMs zu unterstützen), informiert <xref:System.Transactions> den Ressourcen-Manager durch Aufrufen der <xref:System.Transactions.ITransactionPromoter.Promote%2A>-Methode für die <xref:System.Transactions.ITransactionPromoter>-Schnittstelle, von der die <xref:System.Transactions.IPromotableSinglePhaseNotification>-Schnittstelle abgeleitet wurde. Der Ressourcen-Manager konvertiert die Transaktion dann intern von einer lokalen Transaktion (die keine Protokollierung erfordert) in ein Transaktionsobjekt, das an einer DTC-Transaktion teilnehmen kann, und ordnet es den bereits erledigten Aufgaben zu. Wenn der Commit der Transaktion angefordert wird, sendet der Transaktions-Manager auch in diesem Fall die <xref:System.Transactions.IPromotableSinglePhaseNotification.SinglePhaseCommit%2A>-Benachrichtigung an den Ressourcen-Manager, der einen Commit für die verteilte Transaktion ausführt, die er während der Eskalation erstellt hat.

> [!NOTE]
> Die **Transaktions-Ablauf** Verfolgungen (die generiert werden, wenn ein Commit für die eskalierte Transaktion aufgerufen wird) enthalten die Aktivitäts-ID der DTC-Transaktion.

Weitere Informationen zur Ausweitung der Verwaltung finden Sie unter [Ausweitung der Transaktions Verwaltung](transaction-management-escalation.md).

## <a name="transaction-management-escalation-scenario"></a>Eskalationsszenario der Transaktionsverwaltung

Das folgende Szenario veranschaulicht die Eskalation zu einer verteilten Transaktion unter Verwendung des <xref:System.Data>-Namespace als 'Proxy' für den Ressourcen-Manager. Bei diesem Szenario wird vorausgesetzt, dass bereits eine <xref:System.Data>-Verbindung (CN1) zur Datenbank besteht, die von der Transaktion betroffen ist, und dass die Anwendung eine weitere <xref:System.Data>-Verbindung (CN2) einbeziehen will. Die Transaktion muss als vollständig verteilte Zweiphasencommit-Transaktion zum DTC eskaliert werden.

In diesem Szenario:

1. ruft CN1 die <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>-Methode auf, um sich in die Transaktion einzutragen. Dann ist die Transaktion weiterhin lokal, und es gibt keine anderen heraufstufbaren Eintragungen für die Transaktion, weshalb der <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>-Aufruf erfolgreich ist.

2. Wenn die zweite Verbindung, CN2, <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> aufruft, schlägt der Aufruf fehl, da eine andere erweiterbare Eintragung betroffen ist. Deswegen muss CN2 eine DTC-Transaktion abrufen, um sie an SQL zu übergeben. Zu diesem Zweck verwendet die Verbindung eine der Methoden, die von der <xref:System.Transactions.TransactionInterop>-Klasse bereitgestellt werden, um ein Transaktionsformat zu erzeugen, das an SQL übergeben werden kann.

3. <xref:System.Transactions> ruft die <xref:System.Transactions.ITransactionPromoter.Promote%2A>-Methode für die <xref:System.Transactions.ITransactionPromoter>-Schnittstelle auf, die von CN1 implementiert wurde.

4. Dann eskaliert CN1 die Transaktion anhand eines Mechanismus, der spezifisch für SQL 2005 und <xref:System.Data> ist.

5. Der Rückgabewert der <xref:System.Transactions.ITransactionPromoter.Promote%2A>-Methode ist ein Bytearray, das ein Weitergabetoken für die Transaktion enthält. <xref:System.Transactions>verwendet dieses propagierungs Token, um eine DTC-Transaktion zu erstellen, die in die lokale Transaktion integriert werden kann.

6. Jetzt kann CN2 die Daten, die sie durch den Aufruf einer der Methoden mit <xref:System.Transactions.TransactionInterop> erhalten hat, dazu verwenden, die Transaktion an SQL zu übergeben.

7. Jetzt sind beide in eine verteilte DTC-Transaktion eingetragen.

## <a name="single-phase-commit-optimization"></a>Optimierung des Einphasencommit

Das Einphasencommit-Protokoll ist zur Laufzeit effizienter, da alle Updates ohne eine explizite Koordination ausgeführt werden. Um diese Optimierung nutzen zu können, sollten Sie anhand der <xref:System.Transactions.ISinglePhaseNotification>-Schnittstelle für die Ressource einen Ressourcen-Manager implementieren und mithilfe der <xref:System.Transactions.Transaction.EnlistDurable%2A>-Methode oder der <xref:System.Transactions.Transaction.EnlistVolatile%2A>-Methode eine Eintragung in eine Transaktion vornehmen. Insbesondere sollte der *EnlistmentOptions* -Parameter gleich <xref:System.Transactions.EnlistmentOptions.None> sein, um sicherzustellen, dass ein einzelnes Phasen-Commit ausgeführt wird.

Da die <xref:System.Transactions.ISinglePhaseNotification>-Schnittstelle von der <xref:System.Transactions.IEnlistmentNotification>-Schnittstelle abgeleitet ist, kann der Ressourcen-Manager, wenn er für Einphasencommit nicht geeignet ist, trotzdem die Zweiphasencommit-Benachrichtigungen empfangen. Wenn der Ressourcen-Manager eine <xref:System.Transactions.ISinglePhaseNotification.SinglePhaseCommit%2A>-Benachrichtigung vom Transaktions-Manager empfängt, sollte er versuchen, die notwendigen Aufgaben für ein Commit auszuführen, und den TM informieren, ob ein Commit oder ein Rollback für die Transaktion ausgeführt werden soll, indem er die Methode <xref:System.Transactions.SinglePhaseEnlistment.Committed%2A>, <xref:System.Transactions.SinglePhaseEnlistment.Aborted%2A> oder <xref:System.Transactions.SinglePhaseEnlistment.InDoubt%2A> des <xref:System.Transactions.SinglePhaseEnlistment>-Parameters aufruft. Die Antwort <xref:System.Transactions.Enlistment.Done%2A> auf die Eintragung in dieser Phase impliziert die Semantik ReadOnly. Deshalb sollten Sie nicht zusätzlich zu den anderen Methoden <xref:System.Transactions.Enlistment.Done%2A> antworten.

Wenn es nur eine flüchtige Eintragung und keine dauerhafte Eintragung gibt, empfängt die flüchtige Eintragung eine Einphasencommit-Benachrichtigung. Wenn flüchtige Eintragungen vorhanden sind, aber nur eine dauerhafte Eintragung, empfangen die flüchtigen Eintragungen ein Zweiphasencommit. Nach Beendigung empfängt die dauerhafte Eintragung ein Einphasencommit.

## <a name="see-also"></a>Siehe auch

- [Eintragen von Ressourcen als Teilnehmer an einer Transaktion](enlisting-resources-as-participants-in-a-transaction.md)
- [Ausführen eines Einphasen- oder Mehrphasencommits für eine Transaktion](committing-a-transaction-in-single-phase-and-multi-phase.md)
