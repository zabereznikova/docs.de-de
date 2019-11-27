---
title: SyncLock-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
ms.openlocfilehash: 0f430edce99513b0de9ef437d70648a128b336b8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352815"
---
# <a name="synclock-statement"></a>SyncLock-Anweisung
Erhält eine exklusive Sperre für einen Anweisungsblock, bevor der-Block ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a>-Komponenten  
 `lockobject`  
 Erforderlich Ausdruck, der zu einem Objekt Verweis ausgewertet wird.  
  
 `block`  
 Optional. Ein Block von-Anweisungen, die ausgeführt werden sollen, wenn die Sperre abgerufen wird.  
  
 `End SyncLock`  
 Beendet einen `SyncLock`-Block.  
  
## <a name="remarks"></a>Hinweise  
 Die `SyncLock`-Anweisung stellt sicher, dass der Anweisungsblock nicht gleichzeitig von mehreren Threads ausgeführt wird. `SyncLock` verhindert, dass jeder Thread den Block eingibt, bis er von keinem anderen Thread ausgeführt wird.  
  
 Die häufigste Verwendung von `SyncLock` besteht darin, Daten vor der gleichzeitigen Aktualisierung durch mehr als einen Thread zu schützen. Wenn die Anweisungen, die die Daten bearbeiten, ohne Unterbrechung in den Abschluss gehen müssen, platzieren Sie Sie in einem `SyncLock`-Block.  
  
 Ein Anweisungsblock, der durch eine exklusive Sperre geschützt ist, wird manchmal als *kritischer Abschnitt*bezeichnet.  
  
## <a name="rules"></a>Regeln  
  
- Verzweigung. Sie können nicht von außerhalb des Blocks in einen `SyncLock` Block verzweigen.  
  
- Objektwert sperren. Der Wert von `lockobject` kann nicht `Nothing`werden. Sie müssen das Lock-Objekt erstellen, bevor Sie es in einer `SyncLock`-Anweisung verwenden.  
  
     Der Wert von `lockobject` kann beim Ausführen eines `SyncLock` Blocks nicht geändert werden. Der Mechanismus erfordert, dass das Sperr Objekt unverändert bleibt.  
  
- Sie [können den Erwartungs](../../../visual-basic/language-reference/operators/await-operator.md) Operator nicht in einem `SyncLock`-Block verwenden.  
  
## <a name="behavior"></a>Verhalten  
  
- Verfahren. Wenn ein Thread die `SyncLock`-Anweisung erreicht, wertet er den `lockobject` Ausdruck aus und hält die Ausführung an, bis er eine exklusive Sperre für das Objekt erhält, das vom Ausdruck zurückgegeben wird. Wenn ein anderer Thread die `SyncLock`-Anweisung erreicht, erhält er erst dann eine Sperre, wenn der erste Thread die `End SyncLock`-Anweisung ausführt.  
  
- Geschützte Daten. Wenn `lockobject` eine `Shared` Variable ist, verhindert die exklusive Sperre, dass ein Thread in einer Instanz der Klasse den `SyncLock` Block ausführt, während er von einem anderen Thread ausgeführt wird. Dies schützt Daten, die von allen Instanzen gemeinsam genutzt werden.  
  
     Wenn `lockobject` eine Instanzvariable (nicht `Shared`) ist, verhindert die Sperre, dass ein Thread, der in der aktuellen Instanz ausgeführt wird, den `SyncLock` Block gleichzeitig mit einem anderen Thread in derselben Instanz ausführt. Dadurch werden die Daten geschützt, die von der einzelnen Instanz verwaltet werden.  
  
- Erwerb und Release. Ein `SyncLock`-Block verhält sich wie eine `Try...Finally` Konstruktion, in der der `Try` Block eine exklusive Sperre für `lockobject` erhält und der `Finally` Block diese freigibt. Aus diesem Grund garantiert der `SyncLock` Block die Freigabe der Sperre, unabhängig davon, wie Sie den Block beenden. Dies gilt auch im Fall einer nicht behandelten Ausnahme.  
  
- Framework-Aufrufe. Der `SyncLock`-Block übernimmt die exklusive Sperre und gibt Sie frei, indem Sie die Methoden `Enter` und `Exit` der `Monitor`-Klasse im <xref:System.Threading>-Namespace aufrufen.  
  
## <a name="programming-practices"></a>Programmierverfahren  
 Der `lockobject` Ausdruck sollte immer zu einem Objekt ausgewertet werden, das exklusiv zu ihrer Klasse gehört. Sie sollten eine `Private` Objekt Variable deklarieren, um Daten zu schützen, die zur aktuellen Instanz gehören, oder eine `Private Shared` Objekt Variable, um die Daten zu schützen, die für alle Instanzen gemeinsam sind.  
  
 Sie sollten das `Me`-Schlüsselwort nicht verwenden, um ein Sperr Objekt für Instanzdaten bereitzustellen. Wenn der Code, der sich außerhalb ihrer Klasse befindet, einen Verweis auf eine Instanz der Klasse enthält, könnte dieser Verweis als Sperr Objekt für einen `SyncLock` Block verwendet werden, der sich vollständig von Ihnen unterscheidet und verschiedene Daten schützt. Auf diese Weise können Ihre Klasse und die andere Klasse verhindern, dass Sie Ihre nicht verknüpften `SyncLock` Blöcke ausführen. Ähnliches Sperren für eine Zeichenfolge können problematisch sein, da jeder andere Code im Prozess, der dieselbe Zeichenfolge verwendet, dieselbe Sperre gemeinsam verwendet.  
  
 Sie sollten auch die `Me.GetType`-Methode nicht verwenden, um ein Sperr Objekt für freigegebene Daten bereitzustellen. Der Grund hierfür ist, dass `GetType` immer dasselbe `Type` Objekt für einen angegebenen Klassennamen zurückgibt. Externer Code könnte `GetType` für Ihre Klasse abrufen und das gleiche Sperr Objekt erhalten, das Sie verwenden. Dies würde dazu führen, dass die beiden Klassen Ihre `SyncLock` Blöcke gegenseitig blockieren.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel zeigt eine Klasse, die eine einfache Liste von Nachrichten verwaltet. Sie enthält die Nachrichten in einem Array und das zuletzt verwendete Element dieses Arrays in einer Variablen. Die `addAnotherMessage` Prozedur erhöht das letzte Element und speichert die neue Nachricht. Diese beiden Vorgänge werden durch die Anweisungen `SyncLock` und `End SyncLock` geschützt, denn nachdem das letzte Element inkrementiert wurde, muss die neue Nachricht gespeichert werden, bevor ein anderer Thread das letzte Element erneut erhöhen kann.  
  
 Wenn die `simpleMessageList`-Klasse eine Liste der Nachrichten für alle Instanzen freigegeben hat, werden die Variablen `messagesList` und `messagesLast` als `Shared`deklariert. In diesem Fall sollte die Variable `messagesLock` ebenfalls `Shared`werden, damit für jede Instanz ein einzelnes Sperr Objekt verwendet werden kann.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Beispiel werden Threads und `SyncLock`verwendet. Solange die `SyncLock`-Anweisung vorhanden ist, ist der Anweisungsblock ein kritischer Abschnitt und `balance` nie eine negative Zahl. Sie können die Anweisungen `SyncLock` und `End SyncLock` auskommentieren, um die Auswirkung der Ausgabe des `SyncLock`-Schlüssel Worts anzuzeigen.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a>Comments  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Übersicht über Synchronisierungsprimitiven](../../../standard/threading/overview-of-synchronization-primitives.md)
