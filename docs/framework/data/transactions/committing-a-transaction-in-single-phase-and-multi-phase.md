---
title: Ausführen eines Einphasen- oder Mehrphasencommits für eine Transaktion
description: Informieren Sie sich über das Commit von Transaktionen in einer oder zwei Phasen in .net. Ein Zweiphasencommit (2PC) muss ausgeführt werden, wenn die Transaktion mehr als eine Ressource umfasst.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 694ea153-e4db-41ae-96ac-9ac66dcb69a9
ms.openlocfilehash: f46c22294da4db017eceb0bfd0b5cb2bb093c0b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147410"
---
# <a name="committing-a-transaction-in-single-phase-and-multi-phase"></a><span data-ttu-id="4e8b1-104">Ausführen eines Einphasen- oder Mehrphasencommits für eine Transaktion</span><span class="sxs-lookup"><span data-stu-id="4e8b1-104">Committing a Transaction in Single-Phase and Multi-Phase</span></span>

<span data-ttu-id="4e8b1-105">Jede in einer Transaktion verwendete Ressource wird von einem Ressourcen-Manager (RM) verwaltet, dessen Aktionen von einem Transaktions-Manager (TM) koordiniert werden.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-105">Each resource used in a transaction is managed by a resource manager (RM), whose actions are coordinated by a transaction manager (TM).</span></span> <span data-ttu-id="4e8b1-106">Im Thema eintragen von [Ressourcen als Teilnehmer in einer Transaktion](enlisting-resources-as-participants-in-a-transaction.md) wird erläutert, wie eine Ressource (oder mehrere Ressourcen) in eine Transaktion eingetragen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-106">The [Enlisting Resources as Participants in a Transaction](enlisting-resources-as-participants-in-a-transaction.md) topic discusses how a resource (or multiple resources) can be enlisted in a transaction.</span></span> <span data-ttu-id="4e8b1-107">In diesem Thema wird erläutert, wie das Ausführen von Commits für Transaktionen unter eingetragenen Ressourcen koordiniert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-107">This topic discusses how transaction commitment can be coordinated among enlisted resources.</span></span>  
  
 <span data-ttu-id="4e8b1-108">Am Ende der Transaktion fordert die Anwendung die Transaktion auf, entweder einen Commit oder Rollback auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-108">At the end of the transaction, the application requests the transaction to be either committed or rolled back.</span></span> <span data-ttu-id="4e8b1-109">Der Transaktions-Manager muss Risiken verhindern, wie sie beispielsweise entstehen, wenn einige Ressourcen-Manager für einen Commit und andere für ein Rollback stimmen.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-109">The transaction manager must eliminate risks like some resource managers voting to commit while others voting to roll back the transaction.</span></span>  
  
 <span data-ttu-id="4e8b1-110">Wenn die Transaktion mehr als eine Ressource umfasst, müssen Sie ein Zweiphasencommit (2PC) ausführen.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-110">If your transaction involves more than one resource, you must perform a two-phase commit (2PC).</span></span> <span data-ttu-id="4e8b1-111">Mit dem Zweiphasencommit-Protokoll (Vorbereitungs- und Commitphase) wird sichergestellt, dass am Ende der Transaktion für alle Änderungen an allen Ressourcen entweder ein vollständiges Commit ausgeführt wurde oder sie vollständig zurückgesetzt wurden.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-111">The two-phase commit protocol (the prepare phase and the commit phase) ensures that when the transaction ends, all changes to all resources are either totally committed or fully rolled back.</span></span> <span data-ttu-id="4e8b1-112">Alle Teilnehmer werden dann über das Endergebnis informiert.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-112">All the participants are then informed of the final result.</span></span> <span data-ttu-id="4e8b1-113">Eine ausführliche Erläuterung des Zweiphasencommit-Protokolls finden Sie im Buch "*Transaction Processing: Concepts and Techniques (Morgan Kaufmann Series in Datenverwaltung Systems) ISBN: 1558601902*" von Jim Gray.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-113">For a detailed discussion of the two-phase commit protocol, please consult the book "*Transaction Processing : Concepts and Techniques (Morgan Kaufmann Series in Data Management Systems) ISBN:1558601902*" by Jim Gray.</span></span>  
  
 <span data-ttu-id="4e8b1-114">Sie können zudem die Leistung der Transaktion optimieren, indem Sie am Einphasencommit-Protokoll teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-114">You can also optimize your transaction's performance by taking part in the Single Phase Commit protocol.</span></span> <span data-ttu-id="4e8b1-115">Weitere Informationen finden Sie unter [Optimization using Single Phase Commit and Promotable Single Phase Notification](optimization-spc-and-promotable-spn.md).</span><span class="sxs-lookup"><span data-stu-id="4e8b1-115">For more information, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](optimization-spc-and-promotable-spn.md).</span></span>  
  
 <span data-ttu-id="4e8b1-116">Wenn Sie lediglich über das Ergebnis einer Transaktion informiert werden, aber am Abstimmen nicht teilnehmen möchten, können Sie sich für das <xref:System.Transactions.Transaction.TransactionCompleted>-Ereignis anmelden.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-116">If you just want to be informed of a transaction's outcome, and do not want to participate in voting, you should register for the <xref:System.Transactions.Transaction.TransactionCompleted> event.</span></span>  
  
## <a name="two-phase-commit-2pc"></a><span data-ttu-id="4e8b1-117">Zweiphasencommit (2PC)</span><span class="sxs-lookup"><span data-stu-id="4e8b1-117">Two-phase Commit (2PC)</span></span>  

 <span data-ttu-id="4e8b1-118">In der ersten Transaktionsphase fragt der Transaktions-Manager jede Ressource ab, um zu ermitteln, ob ein Commit oder ein Rollback für eine Transaktion ausgeführt werden sollte.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-118">In the first transaction phase, the transaction manager queries each resource to determine whether a transaction should be committed or rolled back.</span></span> <span data-ttu-id="4e8b1-119">In der zweiten Transaktionsphase informiert der Transaktions-Manager alle Ressourcen über das Ergebnis seiner Abfragen und ermöglicht ihnen so die Durchführung eventuell erforderlicher Bereinigungen.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-119">In the second transaction phase, the transaction manager notifies each resource of the outcome of its queries, allowing it to perform any necessary cleanup.</span></span>  
  
 <span data-ttu-id="4e8b1-120">Um an einer solchen Transaktion teilnehmen zu können, muss ein Ressourcen-Manager die <xref:System.Transactions.IEnlistmentNotification>-Schnittstelle implementieren, die Methoden bereitstellt, die vom TM während eines 2PC als Benachrichtigungen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-120">To participate in this kind of transaction, a resource manager must implement the <xref:System.Transactions.IEnlistmentNotification> interface, which provides methods that are called by the TM as notifications during a 2PC.</span></span>  <span data-ttu-id="4e8b1-121">Es folgt ein Beispiel für eine solche Implementierung.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-121">The following sample shows an example of such implementation.</span></span>  
  
 [!code-csharp[Tx_Enlist#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_enlist/cs/enlist.cs#2)]
 [!code-vb[Tx_Enlist#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_enlist/vb/enlist.vb#2)]  
  
### <a name="prepare-phase-phase-1"></a><span data-ttu-id="4e8b1-122">Vorbereitungsphase (Phase 1)</span><span class="sxs-lookup"><span data-stu-id="4e8b1-122">Prepare phase (Phase 1)</span></span>  

 <span data-ttu-id="4e8b1-123">Bei Erhalt einer <xref:System.Transactions.CommittableTransaction.Commit%2A>-Anforderung von einer Anwendung initiiert der Transaktions-Manager die Vorbereitungsphase aller eingetragenen Teilnehmer, indem er die <xref:System.Transactions.IEnlistmentNotification.Prepare%2A>-Methode für jede eingetragene Ressource aufruft, um von jeder Ressource ein Abstimmungsergebnis zur Transaktion zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-123">Upon receiving a <xref:System.Transactions.CommittableTransaction.Commit%2A> request from the application, the transaction manager begins the Prepare phase of all the enlisted participants by calling the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method on each enlisted resource, in order to obtain each resource's vote on the transaction.</span></span>  
  
 <span data-ttu-id="4e8b1-124">Der Ressourcen-Manager, der die <xref:System.Transactions.IEnlistmentNotification>-Schnittstelle implementiert, sollte zuerst die <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29>-Methode implementieren, wie das folgende einfache Beispiel zeigt.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-124">Your resource manager that implements the <xref:System.Transactions.IEnlistmentNotification> interface should first implement the <xref:System.Transactions.IEnlistmentNotification.Prepare%28System.Transactions.PreparingEnlistment%29> method as the following simple example shows.</span></span>  
  
```csharp
public void Prepare(PreparingEnlistment preparingEnlistment)  
{  
     Console.WriteLine("Prepare notification received");  
     //Perform work  
  
     Console.Write("reply with prepared? [Y|N] ");  
     c = Console.ReadKey();  
     Console.WriteLine();  
  
     //If work finished correctly, reply with prepared  
     if ((c.KeyChar == 'Y') || (c.KeyChar == 'y'))  
     {  
          preparingEnlistment.Prepared();  
          break;  
     }  
  
     // otherwise, do a ForceRollback  
     else if ((c.KeyChar == 'N') || (c.KeyChar == 'n'))  
     {  
          preparingEnlistment.ForceRollback();  
          break;  
     }  
}  
```  
  
 <span data-ttu-id="4e8b1-125">Wenn der Manager für dauerhafte Ressourcen diesen Aufruf erhält, muss er die Wiederherstellungsinformationen der Transaktion (die nach Abruf der <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A>-Eigenschaft verfügbar sind) sowie eventuelle weitere Informationen protokollieren, die zur Ausführung der vom Commit betroffenen Transaktion erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-125">When the durable resource manager receives this call, it should log the transaction's recovery information (available by retrieving the <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> property) and whatever information is necessary to complete the transaction on commit.</span></span> <span data-ttu-id="4e8b1-126">Dies muss nicht innerhalb der <xref:System.Transactions.IEnlistmentNotification.Prepare%2A>-Methode geschehen, da der RM dies als Arbeitsthread ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-126">This does not need to be performed within the <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> method because the RM can do this on a worker thread.</span></span>  
  
 <span data-ttu-id="4e8b1-127">Wenn der RM seine Vorbereitung abgeschlossen hat, muss er entscheiden, ob ein Commit oder ein Rollback ausgeführt wird, indem er die <xref:System.Transactions.PreparingEnlistment.Prepared%2A>-Methode oder die <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A>-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-127">When the RM has finished its prepare work, it should vote to commit or roll back by calling the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> or <xref:System.Transactions.PreparingEnlistment.ForceRollback%2A> method.</span></span> <span data-ttu-id="4e8b1-128">Beachten Sie, dass die <xref:System.Transactions.PreparingEnlistment>-Klasse eine <xref:System.Transactions.Enlistment.Done%2A>-Methode von der <xref:System.Transactions.Enlistment>-Klasse erbt.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-128">Notice that the <xref:System.Transactions.PreparingEnlistment> class inherits a <xref:System.Transactions.Enlistment.Done%2A> method from the <xref:System.Transactions.Enlistment> class.</span></span> <span data-ttu-id="4e8b1-129">Wenn Sie diese Methode beim <xref:System.Transactions.PreparingEnlistment>-Rückruf während der Vorbereitungsphase aufrufen, informiert sie den TM, dass es sich um eine schreibgeschützte Eintragung handelt (das bedeutet, die Ressourcen-Manager können die transaktionsgeschützten Daten lesen, aber nicht aktualisieren), und der RM erhält keine weiteren Benachrichtigungen vom TM, was das Ergebnis der Transaktion in Phase 2 betrifft.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-129">If you call this method on the <xref:System.Transactions.PreparingEnlistment> callback during the Prepare phase, it informs the TM that it is a Read-Only enlistment (that is, resource managers that can read but cannot update transaction-protected data) and the RM receives no further notifications from the transaction manager as to the outcome of the transaction in phase 2.</span></span>  
  
 <span data-ttu-id="4e8b1-130">Nachdem alle Ressourcen-Manager <xref:System.Transactions.PreparingEnlistment.Prepared%2A> gestimmt haben, wird der Anwendung mitgeteilt, dass das Commit der Transaktion erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-130">The application is told of the successful commitment of the transaction after all the resource managers vote <xref:System.Transactions.PreparingEnlistment.Prepared%2A>.</span></span>  
  
### <a name="commit-phase-phase-2"></a><span data-ttu-id="4e8b1-131">Commitphase (Phase 2)</span><span class="sxs-lookup"><span data-stu-id="4e8b1-131">Commit phase (Phase 2)</span></span>  

 <span data-ttu-id="4e8b1-132">Wenn der TM in der zweiten Phase der Transaktion erfolgreiche Vorbereitungsergebnisse von allen RMs erhält (alle RMs haben am Ende von Phase 1 <xref:System.Transactions.PreparingEnlistment.Prepared%2A> aufgerufen), ruft er die <xref:System.Transactions.IEnlistmentNotification.Commit%2A>-Methode für jeden Ressourcen-Manager auf.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-132">In the second phase of the transaction, if the transaction manager receives successful prepares from all the resource managers (all the resource managers have invoked <xref:System.Transactions.PreparingEnlistment.Prepared%2A> at the end of phase 1), it invokes the <xref:System.Transactions.IEnlistmentNotification.Commit%2A> method for each resource manager.</span></span> <span data-ttu-id="4e8b1-133">Die Ressourcen-Manager können dann die Änderungen dauerhaft übernehmen und den Commit abschließen.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-133">The resource managers can then make the changes durable and complete the commit.</span></span>  
  
 <span data-ttu-id="4e8b1-134">Informiert einer der RMs über das Fehlschlagen der Vorbereitung in Phase 1, ruft der TM die <xref:System.Transactions.IEnlistmentNotification.Rollback%2A>-Methode für jeden RM auf und gibt der Anwendung das Fehlschlagen des Commit bekannt.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-134">If any resource manager reported a failure to prepare in phase 1, the transaction manager invokes the <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> method for each resource manager and indicates the failure of the commit to the application.</span></span>  
  
 <span data-ttu-id="4e8b1-135">Ihr Ressourcen-Manager sollte daher die folgenden Methoden implementieren.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-135">Thus, your resource manager should implement the following methods.</span></span>  
  
```csharp
public void Commit (Enlistment enlistment)  
{  
     // Do any work necessary when commit notification is received  
  
     // Declare done on the enlistment  
     enlistment.Done();  
}  
  
public void Rollback (Enlistment enlistment)  
{  
     // Do any work necessary when rollback notification is received  
  
     // Declare done on the enlistment
     enlistment.Done();
}  
```  
  
 <span data-ttu-id="4e8b1-136">Der RM muss auf der Grundlage des Benachrichtigungstyps alle zum Abschließen der Transaktion erforderlichen Aktionen ausführen und den TM durch Aufrufen der <xref:System.Transactions.Enlistment.Done%2A>-Methode für den <xref:System.Transactions.Enlistment>-Parameter darüber informieren, dass er bereit ist.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-136">The RM should perform any work necessary to finish the transaction based on the notification type, and inform the TM that it has finished by calling <xref:System.Transactions.Enlistment.Done%2A> method on the <xref:System.Transactions.Enlistment> parameter.</span></span> <span data-ttu-id="4e8b1-137">Diese Aufgabe kann als Arbeitsthread ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-137">This work can be done on a worker thread.</span></span> <span data-ttu-id="4e8b1-138">Die Benachrichtigungen der Phase 2 können inline im gleichen Thread erfolgen, mit dem die <xref:System.Transactions.PreparingEnlistment.Prepared%2A>-Methode in Phase 1 aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-138">Note that the phase 2 notifications can happen inline on the same thread that called the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> method in phase 1.</span></span> <span data-ttu-id="4e8b1-139">Daher sollten Sie nach dem <xref:System.Transactions.PreparingEnlistment.Prepared%2A>-Aufruf keine Aufgaben mehr ausführen (z. B. Freigeben von Sperren), die vor dem Empfang der Benachrichtigungen aus Phase 2 abgeschlossen sein müssen.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-139">As such, you should not do any work after the <xref:System.Transactions.PreparingEnlistment.Prepared%2A> call (for example, releasing locks) that you would expect to have completed before receiving the phase 2 notifications.</span></span>  
  
### <a name="implementing-indoubt"></a><span data-ttu-id="4e8b1-140">Implementieren von InDoubt</span><span class="sxs-lookup"><span data-stu-id="4e8b1-140">Implementing InDoubt</span></span>  

 <span data-ttu-id="4e8b1-141">Schließlich sollten Sie die <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A>-Methode für den flüchtigen Ressourcen-Manager implementieren.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-141">Finally, you should implement the <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A> method for the volatile resource manager.</span></span> <span data-ttu-id="4e8b1-142">Diese Methode wird aufgerufen, wenn der Transaktions-Manager den Kontakt zu einem oder mehreren Teilnehmern verliert und ihren Status deshalb nicht kennt.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-142">This method is called if the transaction manager loses contact with one or more participants, so their status is unknown.</span></span> <span data-ttu-id="4e8b1-143">Wenn dieser Fall eintritt, sollten Sie ihn protokollieren, damit Sie später prüfen können, ob einer der Transaktionsteilnehmer in einem inkonsistenten Zustand geblieben ist.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-143">If this occurs, you should log this fact so that you can investigate later whether any of the transaction participants has been left in an inconsistent state.</span></span>  
  
```csharp
public void InDoubt (Enlistment enlistment)  
{  
     // log this  
     enlistment.Done();  
}  
```  
  
## <a name="single-phase-commit-optimization"></a><span data-ttu-id="4e8b1-144">Optimierung des Einphasencommit</span><span class="sxs-lookup"><span data-stu-id="4e8b1-144">Single Phase Commit Optimization</span></span>  

 <span data-ttu-id="4e8b1-145">Das Einphasencommit-Protokoll ist zur Laufzeit effizienter, da alle Updates ohne eine explizite Koordination ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4e8b1-145">The Single Phase Commit protocol is more efficient at run time because all updates are done without any explicit coordination.</span></span> <span data-ttu-id="4e8b1-146">Weitere Informationen zu diesem Protokoll finden Sie unter [Optimization using Single Phase Commit and Promotable Single Phase Notification](optimization-spc-and-promotable-spn.md).</span><span class="sxs-lookup"><span data-stu-id="4e8b1-146">For more information on this protocol, see [Optimization using Single Phase Commit and Promotable Single Phase Notification](optimization-spc-and-promotable-spn.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e8b1-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e8b1-147">See also</span></span>

- [<span data-ttu-id="4e8b1-148">Optimierung mit Einphasencommit und Heraufstufbarer Einphasenbenachrichtigung</span><span class="sxs-lookup"><span data-stu-id="4e8b1-148">Optimization using Single Phase Commit and Promotable Single Phase Notification</span></span>](optimization-spc-and-promotable-spn.md)
- [<span data-ttu-id="4e8b1-149">Eintragen von Ressourcen als Teilnehmer an einer Transaktion</span><span class="sxs-lookup"><span data-stu-id="4e8b1-149">Enlisting Resources as Participants in a Transaction</span></span>](enlisting-resources-as-participants-in-a-transaction.md)
