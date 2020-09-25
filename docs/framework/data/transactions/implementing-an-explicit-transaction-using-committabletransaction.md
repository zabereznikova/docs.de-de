---
title: Implementieren einer expliziten Transaktion mit CommittableTransaction
description: Implementieren Sie mithilfe der CommittableTransaction-Klasse in .net eine explizite Transaktion. Diese Klasse stellte Anwendungen eine explizite Möglichkeit bereit, eine Transaktion zu verwenden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 29efe5e5-897b-46c2-a35f-e599a273acc8
ms.openlocfilehash: 7e1d78b581fcb3c4b2265f1d04cf2aba83faa28a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91182882"
---
# <a name="implementing-an-explicit-transaction-using-committabletransaction"></a>Implementieren einer expliziten Transaktion mit CommittableTransaction

Die <xref:System.Transactions.CommittableTransaction>-Klasse ermöglicht es Anwendungen, Transaktionen explizit zu verwenden, anstatt die <xref:System.Transactions.TransactionScope>-Klasse implizit zu verwenden. Sie ist für Anwendungen nützlich, die dieselben Transaktionen über mehrere Funktionsaufrufe oder mehrere Threadaufrufe hinweg verwenden wollen. Im Unterschied zur <xref:System.Transactions.TransactionScope>-Klasse muss der Autor der Anwendung die <xref:System.Transactions.CommittableTransaction.Commit%2A>-Methode bzw. die <xref:System.Transactions.Transaction.Rollback%2A>-Methode aufrufen, um einen Commit der Transaktion auszuführen oder um sie abzubrechen.  
  
## <a name="overview-of-the-committabletransaction-class"></a>Übersicht über die CommittableTransaction-Klasse  

 Die <xref:System.Transactions.CommittableTransaction>-Klasse ist von der <xref:System.Transactions.Transaction>-Klasse abgeleitet und stellt deshalb die gesamte Funktionalität der letztgenannten bereit. Besonders nützlich ist die <xref:System.Transactions.Transaction.Rollback%2A>-Methode für die <xref:System.Transactions.Transaction>-Klasse, die auch dazu verwendet werden kann, ein Rollback für ein <xref:System.Transactions.CommittableTransaction>-Objekt auszuführen.  
  
 Die <xref:System.Transactions.Transaction>-Klasse ist der <xref:System.Transactions.CommittableTransaction>-Klasse ähnlich, bietet aber keine `Commit`-Methode. Dadurch haben Sie die Möglichkeit, das Transaktionsobjekt (oder Klone davon) an andere Methoden zu übergeben (eventuell solche anderer Threads), während Sie weiter steuern können, wann ein Commit für die Transaktion ausgeführt wird. Der abgerufene Code kann sich für eine Transaktion eintragen und über sie abstimmen, jedoch kann nur der Ersteller des <xref:System.Transactions.CommittableTransaction>-Objekts ein Commit für die Transaktion ausführen.  
  
 Berücksichtigen Sie die folgenden Aspekte, wenn Sie die <xref:System.Transactions.CommittableTransaction>-Klasse verwenden.  
  
- Durch das Erstellen einer <xref:System.Transactions.CommittableTransaction>-Transaktion wird die Ambient-Transaktion nicht festgelegt. Sie müssen die Ambient-Transaktion explizit festlegen und zurücksetzen, um sicherzustellen, dass Ressourcen-Manager im richtigen Transaktionskontext arbeiten. Die aktuelle Ambient-Transaktion wird durch Einstellen der statischen <xref:System.Transactions.Transaction.Current%2A>-Eigenschaft für das globale <xref:System.Transactions.Transaction>-Objekt festgelegt.  
  
- Ein <xref:System.Transactions.CommittableTransaction>-Objekt kann nicht wiederverwendet werden. Nachdem ein Commit oder ein Rollback für ein <xref:System.Transactions.CommittableTransaction>-Objekt ausgeführt wurde, kann es nicht in einer Transaktion wiederverwendet werden. Das heißt, es kann nicht als aktueller Ambient-Transaktionskontext festgelegt werden.  
  
## <a name="creating-a-committabletransaction"></a>Erstellen einer CommittableTransaction  

 Im folgenden Beispiel wird eine neue Instanz von <xref:System.Transactions.CommittableTransaction> erstellt und ein Commit dafür ausgeführt.  
  
 [!code-csharp[Tx_CommittableTx#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/tx_committabletx/cs/committabletxwithsql.cs#1)]
 [!code-vb[Tx_CommittableTx#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/tx_committabletx/vb/committabletxwithsql.vb#1)]  
  
 Durch das Erstellen einer Instanz von <xref:System.Transactions.CommittableTransaction> wird der Ambient-Transaktionskontext nicht automatisch festgelegt. Deshalb sind Vorgänge, die für einen Ressourcen-Manager ausgeführt werden, nicht Teil dieser Transaktion. Die statische <xref:System.Transactions.Transaction.Current%2A>-Eigenschaft für das globale <xref:System.Transactions.Transaction>-Objekt wird dazu verwendet, die Ambient-Transaktion festzulegen oder abzurufen. Die Anwendung muss sie manuell einstellen, um sicherzustellen, dass Ressourcen-Manager an der Transaktion teilnehmen können. Es wird zudem empfohlen, die alte Ambient-Transaktion zu speichern und nach Beendigung aller Vorgänge mit dem <xref:System.Transactions.CommittableTransaction>-Objekt wiederherzustellen.  
  
 Um ein Commit der Transaktion auszuführen, müssen Sie die <xref:System.Transactions.CommittableTransaction.Commit%2A>-Methode explizit aufrufen. Um ein Rollback einer Transaktion auszuführen, müssen Sie die <xref:System.Transactions.Transaction.Rollback%2A>-Methode aufrufen. Beachten Sie, dass alle Ressourcen, die von einer Transaktion betroffen sind, gesperrt bleiben, bis ein Commit oder ein Rollback für eine <xref:System.Transactions.CommittableTransaction> ausgeführt wurde.  
  
 Ein <xref:System.Transactions.CommittableTransaction>-Objekt kann über Funktionsaufrufe und Threads hinweg verwendet werden. Jedoch muss der Anwendungsentwickler Ausnahmen bearbeiten und die <xref:System.Transactions.Transaction.Rollback%28System.Exception%29>-Methode beim Auftreten von Fehlern explizit aufrufen.  
  
## <a name="asynchronous-commit"></a>Asynchroner Commit  

 Die <xref:System.Transactions.CommittableTransaction>-Klasse stellt zudem einen Mechanismus bereit, um ein Commit für eine Transaktion asynchron auszuführen. Ein Transaktionscommit kann viel Zeit in Anspruch nehmen, da eventuell mehrfach auf Datenbanken zugegriffen werden muss. Außerdem bestehen im Netzwerk möglicherweise Wartezeiten aufgrund der Netzwerklatenz. Wenn Sie Deadlocks in Anwendungen mit hohem Durchsatz vermeiden möchten, können Sie einen asynchronen Commit durchführen, um die Transaktionsaufgaben so schnell wie möglich abzuschließen, und den Commitvorgang als Hintergrundaufgabe ausführen. Die <xref:System.Transactions.CommittableTransaction.BeginCommit%2A>-Methode und die <xref:System.Transactions.CommittableTransaction.EndCommit%2A>-Methode der <xref:System.Transactions.CommittableTransaction>-Klasse ermöglichen dies.  
  
 Sie können <xref:System.Transactions.CommittableTransaction.BeginCommit%2A> aufrufen, um den zurückgehaltenen Commit an einen Thread aus dem Threadpool weiterzuleiten. Sie können zudem <xref:System.Transactions.CommittableTransaction.EndCommit%2A> aufrufen, um zu ermitteln, ob ein Commit für die Transaktion ausgeführt wurde. Wenn der Commit aus irgendeinem Grund nicht für die Transaktion ausgeführt wurde, löst <xref:System.Transactions.CommittableTransaction.EndCommit%2A> eine Transaktionsausnahme aus. Wurde der Transaktionscommit zum Zeitpunkt des Aufrufs von <xref:System.Transactions.CommittableTransaction.EndCommit%2A> noch nicht ausgeführt, wird der Aufrufer gesperrt, bis der Commit durchgeführt oder die Transaktion abgebrochen wurde.  
  
 Das einfachste Verfahren, einen asynchronen Commit auszuführen, besteht darin, eine Rückrufmethode einzurichten. Dann erfolgt bei Beendigung des Commit ein Rückruf. Jedoch müssen Sie die <xref:System.Transactions.CommittableTransaction.EndCommit%2A>-Methode für das ursprüngliche <xref:System.Transactions.CommittableTransaction>-Objekt aufrufen, das für den Aufruf verwendet wurde. Um dieses Objekt zu erhalten, können Sie den *iasynkresult* -Parameter der Rückruf Methode herabsetzen, da die-Klasse die- <xref:System.Transactions.CommittableTransaction> <xref:System.IAsyncResult> Klasse implementiert.  
  
 Das folgende Beispiel zeigt, wie ein asynchroner Commit ausgeführt werden kann.  
  
```csharp  
public void DoTransactionalWork()  
{  
     Transaction oldAmbient = Transaction.Current;  
     CommittableTransaction committableTransaction = new CommittableTransaction();  
     Transaction.Current = committableTransaction;  
  
     try  
     {  
          /* Perform transactional work here */  
          // No errors - commit transaction asynchronously  
          committableTransaction.BeginCommit(OnCommitted,null);  
     }  
     finally  
     {  
          //Restore the ambient transaction
          Transaction.Current = oldAmbient;  
     }  
}  
void OnCommitted(IAsyncResult asyncResult)  
{  
     CommittableTransaction committableTransaction;  
     committableTransaction = asyncResult as CommittableTransaction;
     Debug.Assert(committableTransaction != null);  
     try  
     {  
          using(committableTransaction)  
          {  
               committableTransaction.EndCommit(asyncResult);  
          }  
     }  
     catch(TransactionException e)  
     {  
          //Handle the failure to commit  
     }  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Implementieren einer impliziten Transaktion mit Transaktionsbereich](implementing-an-implicit-transaction-using-transaction-scope.md)
- [Verarbeiten von Transaktionen](index.md)
