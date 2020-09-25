---
title: Implementieren einer impliziten Transaktion mit Transaktionsbereich
description: Implementieren Sie eine implizite Transaktion mithilfe der transaktionscope-Klasse in .net. Diese Klasse bietet eine Möglichkeit, einen Codeblock als Teil einer Transaktion zu kennzeichnen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d1706a-1e0c-4c85-9704-75c908372eb9
ms.openlocfilehash: ff2fe64156d5d72773549d78b2e29631905cbb10
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186860"
---
# <a name="implementing-an-implicit-transaction-using-transaction-scope"></a>Implementieren einer impliziten Transaktion mit Transaktionsbereich

Mit der <xref:System.Transactions.TransactionScope>-Klasse lassen sich Codeblöcke einfach als an einer Transaktion beteiligte Codeblöcke markieren, ohne die Transaktion selbst bearbeiten zu müssen. Ein Transaktionsbereich kann die Ambient-Transaktion automatisch auswählen und verwalten. Wegen ihrer einfachen Verwendung und Effizienz wird empfohlen, die <xref:System.Transactions.TransactionScope>-Klasse zur Entwicklung von Transaktionsanwendungen zu verwenden.  
  
 Außerdem müssen Sie keine Ressourcen für die Transaktion explizit eintragen. Jeder <xref:System.Transactions>-Ressourcen-Manager (z. B. SQL Server 2005) kann das Vorhandensein einer vom Bereich erstellten Ambient-Transaktion erkennen und diese automatisch eintragen.  
  
## <a name="creating-a-transaction-scope"></a>Erstellen eines Transaktionsbereichs  

 Es folgt ein Beispiel für die einfache Verwendung der <xref:System.Transactions.TransactionScope>-Klasse.  
  
 [!code-csharp[TransactionScope#1](../../../../samples/snippets/csharp/VS_Snippets_Remoting/TransactionScope/cs/ScopeWithSQL.cs#1)]
 [!code-vb[TransactionScope#1](../../../../samples/snippets/visualbasic/VS_Snippets_Remoting/TransactionScope/vb/ScopeWithSQL.vb#1)]  
  
 Der Transaktionsbereich wird begonnen, sobald ein neues <xref:System.Transactions.TransactionScope>-Objekt erstellt wird.  Wie im Codebeispiel veranschaulicht, empfiehlt es sich, Bereiche mit einer-Anweisung zu erstellen `using` . Die `using` -Anweisung ist sowohl in c# als auch in Visual Basic verfügbar und funktioniert wie ein `try` ...- `finally` Block, um sicherzustellen, dass der Bereich ordnungsgemäß verworfen wird.  
  
 Beim Instanziieren von <xref:System.Transactions.TransactionScope> bestimmt der Transaktions-Manager, an welcher Transaktion der Bereich beteiligt sein soll. Sobald er festgelegt wurde, ist der Bereich immer an dieser Transaktion beteiligt. Die Entscheidung hängt von zwei Faktoren ab: vom Vorhandensein einer umgebenden Transaktion und vom Wert des `TransactionScopeOption`-Parameters im Konstruktor. Die Ambient-Transaktion ist die Transaktion, in der der Code ausgeführt wird. Ein Verweis auf die Ambient-Transaktion kann durch einen Aufruf der statischen <xref:System.Transactions.Transaction.Current%2A?displayProperty=nameWithType>-Eigenschaft der <xref:System.Transactions.Transaction>-Klasse abgerufen werden. Weitere Informationen zur Verwendung dieses Parameters finden Sie im Abschnitt [Verwalten des Transaktions Flusses mit transaktionscopeoption](#ManageTxFlow) in diesem Thema.  
  
## <a name="completing-a-transaction-scope"></a>Vervollständigen eines Transaktionsbereichs  

 Nachdem die Anwendung alle in einer Transaktion auszuführenden Arbeiten abgeschlossen hat, sollten Sie die <xref:System.Transactions.TransactionScope.Complete%2A?displayProperty=nameWithType>-Methode nur einmal aufrufen, um den Transaktions-Manager darüber zu benachrichtigen, dass für die Transaktion ein Commit ausgeführt werden kann. Es wird empfohlen, den-Aufrufvorgang <xref:System.Transactions.TransactionScope.Complete%2A> als letzte-Anweisung im- `using` Block einzufügen.  
  
 Wenn diese Methode nicht aufgerufen wird, wird die Transaktion abgebrochen, da Sie vom Transaktions-Manager als Systemfehler interpretiert wird oder wenn eine Ausnahme ausgelöst wird, die innerhalb des Bereichs der Transaktion ausgelöst wird. Ein Aufruf dieser Methode garantiert aber nicht, dass ein Commit für die Transaktion ausgeführt wird. Dies ist nur eine Möglichkeit, den Transaktions-Manager über den Status zu informieren. Nach dem Aufruf der <xref:System.Transactions.TransactionScope.Complete%2A>-Methode können Sie nicht mehr über die <xref:System.Transactions.Transaction.Current%2A>-Eigenschaft auf die Ambient-Transaktion zugreifen. Wenn Sie dies dennoch versuchen, wird eine Ausnahme ausgelöst.  
  
 Wenn das <xref:System.Transactions.TransactionScope> Objekt die Transaktion anfänglich erstellt hat, erfolgt die tatsächliche Ausführung des Commits für die Transaktion durch den Transaktions-Manager nach der letzten Codezeile im- `using` Block. Wenn die Transaktion nicht erstellt wurde, wird der Commit ausgeführt, wenn <xref:System.Transactions.CommittableTransaction.Commit%2A> vom Besitzer des <xref:System.Transactions.CommittableTransaction>-Objekts aufgerufen wird. An diesem Punkt ruft der Transaktions-Manager die Ressourcen-Manager auf und informiert Sie entweder über einen Commit oder ein Rollback, je nachdem, ob die- <xref:System.Transactions.TransactionScope.Complete%2A> Methode für das-Objekt aufgerufen wurde <xref:System.Transactions.TransactionScope> .  
  
 Die- `using` Anweisung stellt sicher, dass die- <xref:System.Transactions.TransactionScope.Dispose%2A> Methode des- <xref:System.Transactions.TransactionScope> Objekts auch dann aufgerufen wird, wenn eine Ausnahme auftritt. Der Aufruf der <xref:System.Transactions.TransactionScope.Dispose%2A>-Methode kennzeichnet das Ende des Transaktionsbereichs. Ausnahmen, die nach dem Aufrufen dieser Methode eintreten, beeinflussen die Transaktion möglicherweise nicht. Diese Methode stellt auch den vorherigen Zustand der Ambient-Transaktion wieder her.  
  
 Eine <xref:System.Transactions.TransactionAbortedException> wird ausgelöst, wenn eine vom Transaktionsbereich erstellte Transaktion abgebrochen wird. Eine <xref:System.Transactions.TransactionInDoubtException> wird ausgelöst, wenn der Transaktions-Manager nicht entscheiden kann, ob ein Commit ausgeführt werden soll. Wenn ein Commit für die Transaktion ausgeführt wird, wird keine Ausnahme ausgelöst.  
  
## <a name="rolling-back-a-transaction"></a>Ausführen eines Rollbacks für eine Transaktion  

 Wenn ein Rollback für eine Transaktion ausgeführt werden soll, dürfen Sie die <xref:System.Transactions.TransactionScope.Complete%2A>-Methode nicht im Transaktionsbereich aufrufen. Zum Beispiel können Sie eine Ausnahme im Bereich auslösen. Der Rollback wird für die Transaktion ausgeführt, die im Bereich liegt.  
  
## <a name="managing-transaction-flow-using-transactionscopeoption"></a><a name="ManageTxFlow"></a> Verwalten des Transaktions Flusses mithilfe von transaktionscopeoption  

 Transaktionsbereiche können geschachtelt werden, indem eine Methode aufgerufen wird, die ein <xref:System.Transactions.TransactionScope>-Objekt innerhalb einer Methode verwendet, die ihren eigenen Bereich verwendet. Die `RootMethod`-Methode im folgenden Beispiel veranschaulicht dies.  
  
```csharp  
void RootMethod()
{
    using(TransactionScope scope = new TransactionScope())
    {
        /* Perform transactional work here */
        SomeMethod();
        scope.Complete();
    }
}

void SomeMethod()
{
    using(TransactionScope scope = new TransactionScope())
    {
        /* Perform transactional work here */
        scope.Complete();
    }
}
```  
  
 Der oberste Transaktionsbereich wird als Stammbereich bezeichnet.  
  
 Die <xref:System.Transactions.TransactionScope>-Klasse enthält einige überladene Konstruktoren, die eine Enumeration vom Typ <xref:System.Transactions.TransactionScopeOption> akzeptieren, die das Transaktionsverhalten des Bereichs definiert.  
  
 Ein <xref:System.Transactions.TransactionScope>-Objekt verfügt über drei Optionen:  
  
- Verknüpfen der Ambient-Transaktion oder Erstellen einer neuen Transaktion, wenn keine vorhanden ist.  
  
- Definieren eines neuen Stammbereichs, d. h. Starten einer neuen Transaktion und Festlegen dieser Transaktion als neue Ambient-Transaktion in ihrem eigenem Bereich.  
  
- Nicht teilnehmen an einer Transaktion. Daraus resultiert keine Ambient-Transaktion.  
  
 Wenn der Bereich mit <xref:System.Transactions.TransactionScopeOption.Required> instanziiert wird und eine Ambient-Transaktion vorhanden ist, erstellt der Bereich eine Verknüpfung mit dieser Transaktion. Ist keine Ambient-Transaktion vorhanden, erstellt der Bereich eine neue Transaktion und wird zum Stammbereich. Dies ist der Standardwert. Wenn <xref:System.Transactions.TransactionScopeOption.Required> verwendet wird, muss der Code innerhalb des Bereichs kein anderes Verhalten zeigen, gleichgültig, ob es sich um den Stammbereich oder nur um eine Verknüpfung mit der Ambient-Transaktion handelt. Er sollte in beiden Fällen das Gleiche ausführen.  
  
 Wenn der Bereich mit <xref:System.Transactions.TransactionScopeOption.RequiresNew> instanziiert wird, ist er immer der Stammbereich. Er startet eine neue Transaktion, und seine Transaktion wird zur neuen Ambient-Transaktion im Bereich.  
  
 Wird der Bereich mit <xref:System.Transactions.TransactionScopeOption.Suppress> instanziiert, dann ist er nie an einer Transaktion beteiligt, unabhängig davon, ob eine Ambient-Transaktion vorhanden ist. Ein Bereich, der mit diesem Wert instanziiert wird, hat immer `null` als Ambient-Transaktion.  
  
 Die obigen Optionen sind in der folgenden Tabelle zusammengefasst.  
  
|TransactionScopeOption|Ambient-Transaktion|Der Bereich ist beteiligt an|  
|----------------------------|-------------------------|-----------------------------|  
|Erforderlich|Nein|Neue Transaktion (wird zum Stamm)|  
|Requires New|Nein|Neue Transaktion (wird zum Stamm)|  
|Suppress|Nein|Keine Transaktion|  
|Erforderlich|Ja|Ambient-Transaktion|  
|Requires New|Ja|Neue Transaktion (wird zum Stamm)|  
|Suppress|Ja|Keine Transaktion|  
  
 Wenn ein <xref:System.Transactions.TransactionScope>-Objekt eine Verknüpfung mit einer vorhandenen Ambient-Transaktion erstellt, wird die Transaktion unter Umständen nur dann durch die Freigabe des Bereichsobjekts beendet, wenn der Bereich die Transaktion abbricht. Wenn die Ambient-Transaktion vom Stammbereich erstellt wurde, wird die <xref:System.Transactions.CommittableTransaction.Commit%2A>-Methode nur dann für die Transaktion aufgerufen, wenn der Stammbereich gelöscht wird. Wurde die Transaktion manuell erstellt, dann endet die Transaktion, wenn sie abgebrochen oder von ihrem Ersteller die Commit-Methode aufgerufen wird.  
  
 Im folgenden Beispiel werden mit einem <xref:System.Transactions.TransactionScope>-Objekt drei verschachtelte Bereichsobjekte erstellt, die jeweils mit einem anderen <xref:System.Transactions.TransactionScopeOption>-Wert instanziiert werden.  
  
```csharp  
using(TransactionScope scope1 = new TransactionScope())
//Default is Required
{
    using(TransactionScope scope2 = new TransactionScope(TransactionScopeOption.Required))
    {
        //...
    }

    using(TransactionScope scope3 = new TransactionScope(TransactionScopeOption.RequiresNew))
    {
        //...  
    }
  
    using(TransactionScope scope4 = new TransactionScope(TransactionScopeOption.Suppress))
    {
        //...  
    }
}
```  
  
 Im Beispiel wird ein Codeblock ohne Ambient-Transaktion gezeigt, in dem ein neuer Bereich (`scope1`) mit <xref:System.Transactions.TransactionScopeOption.Required> erstellt wird. Der Bereich `scope1` ist ein Stammbereich, da er eine neue Transaktion (Transaction A) erstellt und Transaction A als Ambient-Transaktion definiert. `Scope1` erstellt dann drei weitere Objekte, die jeweils über einen anderen <xref:System.Transactions.TransactionScopeOption> Wert verfügen. Beispielsweise wird `scope2` mit <xref:System.Transactions.TransactionScopeOption.Required> erstellt, und da eine Ambient-Transaktion vorhanden ist, wird eine Verknüpfung mit der ersten von `scope1` erstellten Transaktion erstellt. Beachten Sie, dass `scope3` der Stammbereich der neuen Transaktion ist, und dass `scope4` keine Ambient-Transaktion enthält.  
  
 Der am häufigsten verwendete Wert und Standardwert von <xref:System.Transactions.TransactionScopeOption> lautet zwar <xref:System.Transactions.TransactionScopeOption.Required>, aber auch die anderen Werte erfüllen jeweils einen bestimmten Zweck.  

### <a name="non-transactional-code-inside-a-transaction-scope"></a>Nicht transaktionaler Code innerhalb eines Transaktions Bereichs

 <xref:System.Transactions.TransactionScopeOption.Suppress> ist nützlich, wenn Sie die vom Code Abschnitt ausgeführten Vorgänge beibehalten möchten und die Ambient-Transaktion nicht abbrechen möchten, wenn die Vorgänge fehlschlagen. Wenn beispielsweise Aktivitäten protokolliert oder Überwachungsoperationen ausgeführt werden sollen oder wenn Ereignisse für Abonnenten veröffentlicht werden sollen, unabhängig davon, ob die Ambient-Transaktion abgeschlossen oder abgebrochen wird. Dieser Wert ermöglicht es, wie im folgenden Beispiel gezeigt, in einen Transaktionsbereich einen von der Transaktion unabhängigen Codeabschnitt einzufügen.  
  
```csharp  
using(TransactionScope scope1 = new TransactionScope())
{
    try
    {
        //Start of non-transactional section
        using(TransactionScope scope2 = new
            TransactionScope(TransactionScopeOption.Suppress))  
        {  
            //Do non-transactional work here  
        }  
        //Restores ambient transaction here
   }
   catch {}  
   //Rest of scope1
}
```  
  
### <a name="voting-inside-a-nested-scope"></a>Abstimmen in einem geschachtelten Bereich  

 Obwohl ein verschachtelter Bereich eine Verknüpfung mit der Ambient-Transaktion des Stammbereichs erstellen kann, wirkt sich ein Aufruf von <xref:System.Transactions.TransactionScope.Complete%2A> im verschachtelten Bereich nicht auf den Stammbereich aus. Nur wenn alle Bereiche vom Stammbereich bis zum letzten verschachtelten Bereich dafür stimmen, dass ein Commit für eine Transaktion ausgeführt wird, wird die Transaktion abgeschlossen. Wenn <xref:System.Transactions.TransactionScope.Complete%2A> nicht in einem geschachtelten Bereich aufgerufen wird, wirkt sich dies auf den Stammbereich aus, da die Ambient-Transaktion sofort abgebrochen wird.  
  
## <a name="setting-the-transactionscope-timeout"></a>Festlegen des TransactionScope-Timeouts  

 Einige der überladenen Konstruktoren von <xref:System.Transactions.TransactionScope> akzeptieren einen Wert vom Typ <xref:System.TimeSpan>, der zur Steuerung des Timeouts einer Transaktion dient. Ein Timeout mit dem Wert Null (0) steht für ein unendliches Timeout. Ein unendliches Timeout ist vor allem beim Debuggen hilfreich, wenn ein Problem in der Geschäftslogik durch das schrittweise Ausführen des Codes eingegrenzt werden soll, und wenn während der Suche nach der Problemursache bei der Transaktion, die untersucht wird, kein Timeout auftreten soll. Verwenden Sie den unendlichen Timeoutwert in allen anderen Fällen mit äußerster Vorsicht, weil dadurch die Sicherungsmechanismen gegen Transaktions-Deadlocks außer Kraft gesetzt werden.  
  
 Sie legen den <xref:System.Transactions.TransactionScope>-Timeout i.&#160;d.&#160;R. in zwei Fällen auf einen anderen Wert als den Standardwert fest. Erstens während der Entwicklung, wenn Sie testen möchten, wie eine Anwendung mit abgebrochenen Transaktionen umgeht. Wenn Sie für den Timeout einen kleinen Wert (z.&#160;B. eine Millisekunde) angeben, kann dies zum Fehlschlagen der Transaktion führen, und Sie können folglich den Fehlerbehandlungscode überprüfen. Zweitens wählen Sie einen kleineren Wert als den Standardtimeoutwert, wenn Sie annehmen, dass der Bereich zu einem Ressourcenkonflikt beiträgt, der zu Deadlocks führt. In diesem Fall soll die Transaktion so bald wie möglich abgebrochen werden und nicht auf den Ablauf des Standardtimeouts warten.  
  
 Wenn in einem Bereich eine Verknüpfung mit einer Ambient-Transaktion hergestellt wird, aber ein kleinerer Timeoutwert als der für die Ambient-Transaktion definierte Wert angegeben wird, dann wird der neue kürzere Timeoutwert für das <xref:System.Transactions.TransactionScope>-Objekt übernommen. Wird der Bereich hier nicht innerhalb der in der Ambient-Transaktion angegebenen Zeitspanne beendet, wird die Transaktion automatisch beendet. Wenn der Timeoutwert des geschachtelten Bereichs größer ist als der der Ambient-Transaktion, hat er keine Auswirkungen.  
  
## <a name="setting-the-transactionscope-isolation-level"></a>Festlegen der TransactionScope-Isolationsstufe  

 Einige der überladenen Konstruktoren von <xref:System.Transactions.TransactionScope> akzeptieren neben dem Timeoutwert eine Struktur vom Typ <xref:System.Transactions.TransactionOptions> zur Festlegung der Isolationsstufe. Standardmäßig wird zur Ausführung einer Transaktion die Isolationsstufe auf <xref:System.Transactions.IsolationLevel.Serializable> festgelegt. Häufig wird für Systeme, die viele Lesevorgänge ausführen müssen, eine andere Isolationsstufe als <xref:System.Transactions.IsolationLevel.Serializable> gewählt. Dies erfordert ein umfassendes Verständnis der Transaktionsverarbeitungstheorie und der Semantik der betreffenden Transaktion, der einschlägigen Parallelitätsprobleme und der Auswirkungen auf die Systemkonsistenz.  
  
 Überdies unterstützen nicht alle Ressourcen-Manager alle Isolationsstufen, sodass ein Ressourcen-Manager die Transaktion möglicherweise auf einer höheren als der konfigurierten Isolationsstufe bearbeitet.  
  
 Jede Isolationsstufe außer <xref:System.Transactions.IsolationLevel.Serializable> ist für Inkonsistenzen anfällig, die sich daraus ergeben können, dass andere Transaktionen auf die gleichen Informationen zugreifen. Die verschiedenen Isolationsstufen unterscheiden sich darin, wie Lese- und Schreibsperren verwendet werden. Eine Sperre kann nur dann gelten, wenn die Transaktion im Ressourcen-Manager auf Daten zugreift. Sie kann aber solange gelten, bis die Transaktion abgeschlossen oder abgebrochen wurde. Im ersten Fall ist der Durchsatz höher, im zweiten Fall die Konsistenz. Da es zwei Arten von Sperren und zwei Arten von Operationen (Lesen/Schreiben) gibt, sind vier grundlegende Isolationsstufen verfügbar. Weitere Informationen finden Sie unter <xref:System.Transactions.IsolationLevel>.  
  
 Beim Einsatz verschachtelter <xref:System.Transactions.TransactionScope>-Objekte muss für alle verschachtelten Bereiche die gleiche Isolationsstufe konfiguriert werden, wenn eine Verknüpfung mit der Ambient-Transaktion hergestellt werden soll Wenn verschachtelte <xref:System.Transactions.TransactionScope>-Objekte eine Verknüpfung mit der Ambient-Transaktion herzustellen versuchen und für diese eine andere Isolationsstufe festgelegt wurde, dann wird eine Ausnahme des Typs <xref:System.ArgumentException> ausgelöst.  
  
## <a name="interop-with-com"></a>Zusammenarbeit mit COM+  

 Wenn Sie eine neue <xref:System.Transactions.TransactionScope>-Instanz erstellen, können Sie die <xref:System.Transactions.EnterpriseServicesInteropOption>-Enumeration in einem der Konstruktoren verwenden, um die Zusammenarbeit mit COM+ näher zu bestimmen. Weitere Informationen hierzu finden Sie unter [Interoperabilität mit Enterprise Services und com+-Transaktionen](interoperability-with-enterprise-services-and-com-transactions.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Transactions.Transaction.Clone%2A>
- <xref:System.Transactions.TransactionScope>
