---
title: SyncLock-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: a2bd6ca11072113d8acff78032c19d48c30933c3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615128"
---
# <a name="synclock-statement"></a>SyncLock-Anweisung
Ruft eine exklusive Sperre für einen Anweisungsblock vor der Ausführung des Blocks ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a>Teile  
 `lockobject`  
 Erforderlich. Ein Ausdruck, einen Objektverweis ausgewertet wird.  
  
 `block`  
 Dies ist optional. Der Block von Anweisungen, die ausgeführt werden, wenn die Sperre abgerufen wurde.  
  
 `End SyncLock`  
 Beendet eine `SyncLock` Block.  
  
## <a name="remarks"></a>Hinweise  
 Die `SyncLock` Anweisung wird sichergestellt, dass den Anweisungsblock nicht von mehreren Threads gleichzeitig ausgeführt wird. `SyncLock` verhindert, dass jeder Thread den Block eingeben, bis kein anderer Thread sie ausgeführt wird.  
  
 Die häufigste Verwendung von `SyncLock` zum Schutz von Daten aus, die gleichzeitig von mehreren Threads aktualisiert wird. Wenn die Anweisungen, die die Daten bearbeiten können bis zum Abschluss ohne Unterbrechung wechseln müssen, platzieren Sie sie in einem `SyncLock` Block.  
  
 Ein Anweisungsblock, die durch eine exklusive Sperre geschützt wird auch als bezeichnet. eine *kritischen Abschnitt*.  
  
## <a name="rules"></a>Regeln  
  
- Branch. Sie können keine branch in einen `SyncLock` Blockieren von außerhalb des Blocks.  
  
- Der Wert der Sperre-Objekts. Der Wert des `lockobject` nicht `Nothing`. Sie müssen das Sperrobjekt erstellen, bevor Sie ihn im Verwenden einer `SyncLock` Anweisung.  
  
     Sie können den Wert nicht ändern `lockobject` während der Ausführung einer `SyncLock` Block. Der Mechanismus ist erforderlich, dass das Sperrobjekt unverändert bleiben.  
  
- Können keine der ["await"](../../../visual-basic/language-reference/operators/await-operator.md) -Operator in einem `SyncLock` Block.  
  
## <a name="behavior"></a>Verhalten  
  
- Mechanismus. Wenn ein Thread erreicht die `SyncLock` -Anweisung, es ergibt die `lockobject` Ausdruck und angehalten, bis er eine exklusive Sperre für das Objekt, das vom Ausdruck zurückgegebene erhält. Wenn ein anderer Thread erreicht die `SyncLock` -Anweisung, es ist nicht Ruft eine Sperre, bis der erste Thread führt die `End SyncLock` Anweisung.  
  
- Stellen Sie geschützte Daten. Wenn `lockobject` ist eine `Shared` Variablen, die exklusive Sperre verhindert, dass einen Thread in jeder Instanz der Klasse Ausführen der `SyncLock` zu blockieren, während alle anderen Thread ausgeführt wird. Dies schützt die Daten, die von allen Instanzen gemeinsam verwendet werden.  
  
     Wenn `lockobject` ist eine Instanzvariable (nicht `Shared`), die Sperre verhindert einen Thread, in der aktuellen Instanz der Ausführung der `SyncLock` Block zur gleichen Zeit wie ein anderer Thread in der gleichen Instanz. Dies schützt die Daten, die von den einzelnen Instanzen verwaltet wird.  
  
- Abruf und die Freigabe. Ein `SyncLock` Block verhält sich wie ein `Try...Finally` Konstruktion, in dem die `Try` Block erhält eine exklusive Sperre auf `lockobject` und `Finally` Block freigegeben wird. Aus diesem Grund die `SyncLock` Block gewährleistet die Aufhebung der Sperre, unabhängig davon, wie Sie den Block zu beenden. Dies gilt auch im Falle einer nicht behandelten Ausnahme.  
  
- Framework-Aufrufe. Die `SyncLock` Block erhält und hebt die exklusive Sperre durch Aufrufen der `Enter` und `Exit` Methoden der `Monitor` -Klasse in der <xref:System.Threading> Namespace.  
  
## <a name="programming-practices"></a>Methoden für die Programmierung  
 Die `lockobject` Ausdruck ergeben sollten immer ein Objekt, das ausschließlich auf die Klasse gehört. Deklarieren Sie eine `Private` Objektvariable zum Schutz von Daten, die auf die aktuelle Instanz gehören oder `Private Shared` Objektvariable, um Daten in allen Instanzen häufig zu schützen.  
  
 Verwenden Sie nicht die `Me` Schlüsselwort, um eine Sperre geben z. B. Objektdaten. Wenn Code außerhalb der Klasse einen Verweis auf eine Instanz der Klasse enthält, können sie diesen Verweis verwenden, als Sperrobjekt für eine `SyncLock` blockieren, die von ihren Bildschirmen, grundlegend andere Daten geschützt werden. Auf diese Weise Ihre Klasse und die andere Klasse können einander blockieren hindert, die nicht verknüpfte `SyncLock` Blöcke. Auf ähnliche Weise Sperren für eine Zeichenfolge kann problematisch sein, da es sich bei jedem anderen Code in den Prozess über die gleiche Zeichenfolge die gleiche Sperre freigibt.  
  
 Sie sollten auch nicht verwenden, die `Me.GetType` freigegebene Methode, um ein Sperrobjekt für bereitzustellen. Grund hierfür ist, `GetType` gibt immer die gleiche `Type` Objekt für einen bestimmten Klassennamen. Externer Code Aufrufen `GetType` für Ihre Klasse und rufen Sie die gleiche Sperrobjekt, das Sie verwenden. Dies führt zu die beiden Klassen, dass die von ihren `SyncLock` Blöcke.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel zeigt eine Klasse, die eine einfache Liste von Nachrichten verwaltet. Sie enthält die Nachrichten in einem Array und das letzte Element dieses Arrays in eine Variable verwendet. Die `addAnotherMessage` Prozedur erhöht das letzte Element und speichert die neue Meldung. Diese beiden Vorgänge sind geschützt, indem die `SyncLock` und `End SyncLock` -Anweisungen, da nach das letzte Element erhöht wurde, die neue Nachricht gespeichert werden muss, bevor ein anderer Thread das letzte Element erneut erhöhen kann.  
  
 Wenn die `simpleMessageList` Klasse freigegeben, eine Liste von Nachrichten auf alle zugehörigen Instanzen, die Variablen `messagesList` und `messagesLast` deklariert werden würde, als `Shared`. In diesem Fall ist die Variable `messagesLock` außerdem sollte der `Shared`, sodass es gäbe eine einzige Sperre-Objekt, das von jeder Instanz verwendet wird.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Beispiel wird die Threads und `SyncLock`. Solange die `SyncLock` Anweisung vorhanden ist, der Anweisungsblock ein Kritischer Abschnitt und `balance` wird nie eine negative Zahl. Können Sie Auskommentieren der `SyncLock` und `End SyncLock` Anweisungen, um die Auswirkungen der auslassen finden Sie unter den `SyncLock` Schlüsselwort.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a>Kommentare  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Übersicht über Synchronisierungsprimitiven](../../../standard/threading/overview-of-synchronization-primitives.md)
