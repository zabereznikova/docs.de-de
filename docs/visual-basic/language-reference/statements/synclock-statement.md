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
ms.openlocfilehash: fd932a20af274faf2b56136a94675b28399989b8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404160"
---
# <a name="synclock-statement"></a>SyncLock-Anweisung
Erhält eine exklusive Sperre für einen Anweisungsblock, bevor der-Block ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a>Bestandteile  
 `lockobject`  
 Erforderlich. Ausdruck, der zu einem Objekt Verweis ausgewertet wird.  
  
 `block`  
 Optional. Ein Block von-Anweisungen, die ausgeführt werden sollen, wenn die Sperre abgerufen wird.  
  
 `End SyncLock`  
 Beendet einen- `SyncLock` Block.  
  
## <a name="remarks"></a>Bemerkungen  
 Die- `SyncLock` Anweisung stellt sicher, dass der Anweisungsblock nicht gleichzeitig von mehreren Threads ausgeführt wird. `SyncLock`verhindert, dass jeder Thread den Block eingibt, bis er von keinem anderen Thread ausgeführt wird.  
  
 Die häufigste Verwendung von `SyncLock` besteht darin, Daten vor der gleichzeitigen Aktualisierung durch mehr als einen Thread zu schützen. Wenn die Anweisungen, die die Daten bearbeiten, ohne Unterbrechung in den Abschluss gehen müssen, platzieren Sie Sie in einem- `SyncLock` Block.  
  
 Ein Anweisungsblock, der durch eine exklusive Sperre geschützt ist, wird manchmal als *kritischer Abschnitt*bezeichnet.  
  
## <a name="rules"></a>Regeln  
  
- Verzweigung. Sie können nicht von außerhalb des-Blocks in einen-Block verzweigen `SyncLock` .  
  
- Objektwert sperren. Der Wert von `lockobject` darf nicht sein `Nothing` . Sie müssen das Lock-Objekt erstellen, bevor Sie es in einer- `SyncLock` Anweisung verwenden.  
  
     Der Wert von kann `lockobject` beim Ausführen eines-Blocks nicht geändert werden `SyncLock` . Der Mechanismus erfordert, dass das Sperr Objekt unverändert bleibt.  
  
- Sie [können den Erwartungs](../operators/await-operator.md) Operator nicht in einem- `SyncLock` Block verwenden.  
  
## <a name="behavior"></a>Verhalten  
  
- Verfahren. Wenn ein Thread die- `SyncLock` Anweisung erreicht, wertet er den Ausdruck aus und hält die `lockobject` Ausführung an, bis er eine exklusive Sperre für das Objekt erhält, das vom Ausdruck zurückgegeben wird. Wenn ein anderer Thread die- `SyncLock` Anweisung erreicht, erhält er erst dann eine Sperre, wenn der erste Thread die- `End SyncLock` Anweisung ausführt.  
  
- Geschützte Daten. Wenn `lockobject` eine `Shared` Variable ist, verhindert die exklusive Sperre, dass ein Thread in einer Instanz der Klasse den Block ausführt, `SyncLock` während er von einem anderen Thread ausgeführt wird. Dies schützt Daten, die von allen Instanzen gemeinsam genutzt werden.  
  
     Wenn `lockobject` eine Instanzvariable (nicht `Shared` ) ist, verhindert die Sperre, dass ein Thread, der in der aktuellen Instanz ausgeführt wird, den `SyncLock` Block gleichzeitig mit einem anderen Thread in derselben Instanz ausführt. Dadurch werden die Daten geschützt, die von der einzelnen Instanz verwaltet werden.  
  
- Erwerb und Release. Ein- `SyncLock` Block verhält sich wie eine `Try...Finally` Konstruktion, bei der der `Try` -Block eine exklusive Sperre für abruft `lockobject` und der-Block `Finally` Sie freigibt. Aus diesem Grund garantiert der- `SyncLock` Block die Freigabe der Sperre, unabhängig davon, wie Sie den Block beenden. Dies gilt auch im Fall einer nicht behandelten Ausnahme.  
  
- Framework-Aufrufe. Der `SyncLock` -Block Ruft die exklusive Sperre ab und gibt Sie frei, indem Sie die `Enter` -und- `Exit` Methoden der- `Monitor` Klasse im- <xref:System.Threading> Namespace aufrufen.  
  
## <a name="programming-practices"></a>Programmierverfahren  
 Der `lockobject` Ausdruck sollte immer zu einem Objekt ausgewertet werden, das exklusiv zu ihrer Klasse gehört. Sie sollten eine- `Private` Objekt Variable deklarieren, um Daten zu schützen, die zur aktuellen Instanz gehören, oder eine- `Private Shared` Objekt Variable, um die Daten zu schützen, die für alle Instanzen  
  
 Sie sollten das- `Me` Schlüsselwort nicht verwenden, um ein Sperr Objekt für Instanzdaten bereitzustellen. Wenn der Code, der sich außerhalb ihrer Klasse befindet, einen Verweis auf eine Instanz der Klasse aufweist, könnte dieser Verweis als Sperr Objekt für einen `SyncLock` Block verwendet werden, der sich vollständig von Ihnen unterscheidet und verschiedene Daten schützt. Auf diese Weise können Ihre Klasse und die andere Klasse verhindern, dass Sie Ihre nicht verbundenen `SyncLock` Blöcke ausführen. Ähnliches Sperren für eine Zeichenfolge können problematisch sein, da jeder andere Code im Prozess, der dieselbe Zeichenfolge verwendet, dieselbe Sperre gemeinsam verwendet.  
  
 Sie sollten auch die-Methode nicht verwenden `Me.GetType` , um ein Sperr Objekt für freigegebene Daten bereitzustellen. Dies liegt daran, dass `GetType` `Type` für einen angegebenen Klassennamen immer das gleiche Objekt zurückgibt. Externer Code könnte `GetType` für Ihre Klasse aufzurufen und das gleiche Sperr Objekt erhalten, das Sie verwenden. Dies würde dazu führen, dass die beiden Klassen Ihre Blöcke gegenseitig blockieren `SyncLock` .  
  
## <a name="examples"></a>Beispiele  
  
### <a name="description"></a>BESCHREIBUNG  
 Das folgende Beispiel zeigt eine Klasse, die eine einfache Liste von Nachrichten verwaltet. Sie enthält die Nachrichten in einem Array und das zuletzt verwendete Element dieses Arrays in einer Variablen. Die `addAnotherMessage` Prozedur erhöht das letzte Element und speichert die neue Nachricht. Diese beiden Vorgänge werden durch die `SyncLock` -und- `End SyncLock` Anweisungen geschützt, denn sobald das letzte Element inkrementiert wurde, muss die neue Nachricht gespeichert werden, bevor ein anderer Thread das letzte Element erneut erhöhen kann.  
  
 Wenn die `simpleMessageList` Klasse eine Liste von Nachrichten für alle Instanzen freigegeben hat, `messagesList` werden die Variablen und `messagesLast` als deklariert `Shared` . In diesem Fall sollte die Variable `messagesLock` auch sein `Shared` , sodass es ein einzelnes Sperr Objekt gibt, das von jeder Instanz verwendet wird.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrThreading#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/Class1.vb#1)]  
  
### <a name="description"></a>BESCHREIBUNG  
 Im folgenden Beispiel werden Threads und verwendet `SyncLock` . Solange die- `SyncLock` Anweisung vorhanden ist, ist der Anweisungsblock ein kritischer Abschnitt und `balance` wird nie eine negative Zahl sein. Sie können die `SyncLock` -Anweisung und die-Anweisung auskommentieren `End SyncLock` , um die Auswirkung des auslassen des `SyncLock` Schlüssel Worts anzuzeigen.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrThreading#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrThreading/VB/class2.vb#21)]  
  
### <a name="comments"></a>Kommentare  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [Übersicht über Synchronisierungsprimitiven](../../../standard/threading/overview-of-synchronization-primitives.md)
