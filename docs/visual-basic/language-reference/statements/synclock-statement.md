---
title: SyncLock-Anweisung
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c363b41bb7a409c490a6e07d4a1a4f1bb44c1438
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
 Erforderlich. Ein Ausdruck, der einen Objektverweis ergibt.  
  
 `block`  
 Dies ist optional. Der Block von Anweisungen, die ausgeführt werden, wenn die Sperre abgerufen wurde.  
  
 `End SyncLock`  
 Beendet eine `SyncLock` Block.  
  
## <a name="remarks"></a>Hinweise  
 Die `SyncLock` -Anweisung sicher, dass den Anweisungsblock nicht von mehreren Threads gleichzeitig ausgeführt werden. `SyncLock`verhindert, dass jeder Thread den Block eintritt, bis keine anderen Thread ausgeführt wird.  
  
 Die häufigste Verwendung von `SyncLock` zu verhindern, dass Daten von mehreren Threads gleichzeitig aktualisiert wird. Wenn die Anweisungen, die die Daten bearbeiten können bis zum Abschluss ohne Unterbrechung wechseln müssen, platzieren Sie sie innerhalb einer `SyncLock` Block.  
  
 Ein Anweisungsblock geschützt durch eine exklusive Sperre bezeichnet eine *kritischen Abschnitt*.  
  
## <a name="rules"></a>Regeln  
  
-   Verzweigen. Sie können keine Verzweigung in einer `SyncLock` Blockieren von außerhalb des Blocks.  
  
-   Der Wert der Lock-Objekts. Der Wert der `lockobject` nicht `Nothing`. Sie müssen das Sperrenobjekt erstellen, bevor Sie es im Verwenden einer `SyncLock` Anweisung.  
  
     Sie können den Wert der ändern `lockobject` während der Ausführung eine `SyncLock` Block. Der Mechanismus ist erforderlich, dass das Sperrobjekt unverändert bleiben.  
  
-   Können Sie keine der ["await"](../../../visual-basic/language-reference/operators/await-operator.md) Operator in einem `SyncLock` Block.  
  
## <a name="behavior"></a>Verhalten  
  
-   Mechanismus. Wenn ein Thread erreicht die `SyncLock` -Anweisung ausgewertet den `lockobject` Ausdruck und hält die Ausführung bis er eine exklusive Sperre für das Objekt, das von dem Ausdruck zurückgegeben erhält. Wenn ein anderer Thread erreicht die `SyncLock` -Anweisung, erwirbt er eine Sperre, bis der erste Thread führt die `End SyncLock` Anweisung.  
  
-   Stellen Sie geschützte Daten. Wenn `lockobject` ist ein `Shared` Variable, die exklusive Sperre verhindert, dass einen Thread in jeder Instanz der Klasse Ausführen der `SyncLock` blockieren, während ein anderer Thread ausgeführt wird. Dies schützt die Daten, die von allen Instanzen gemeinsam genutzt werden.  
  
     Wenn `lockobject` wird von eine Instanzvariablen (nicht `Shared`), die Sperre verhindert, dass einen Thread in der aktuellen Instanz ausgeführt wird, verhindern Sie die Ausführung der `SyncLock` Block zur gleichen Zeit wie ein anderer Thread in der gleichen Instanz. Dies schützt die Daten, die von einzelnen Instanzen verwaltet.  
  
-   Erhalt und die Freigabe. Ein `SyncLock` Block verhält sich wie ein `Try...Finally` Konstruktion, in dem die `Try` Block erhält eine exklusive Sperre auf `lockobject` und die `Finally` Block freigibt. Aus diesem Grund die `SyncLock` Block wird sichergestellt, Freigabe der Sperre, unabhängig davon, wie Sie den Block zu beenden. Dies gilt sogar im Fall einer nicht behandelten Ausnahme.  
  
-   Framework-Aufrufe. Die `SyncLock` -Block erwirbt und hebt die exklusive Sperre durch Aufrufen der `Enter` und `Exit` Methoden die `Monitor` -Klasse in der <xref:System.Threading> Namespace.  
  
## <a name="programming-practices"></a>Programmierung-Methoden  
 Die `lockobject` Ausdruck ergeben sollten immer ein Objekt, das ausschließlich auf die Klasse gehört. Deklarieren Sie eine `Private` Object-Variablen zum Schützen von Daten, die auf die aktuelle Instanz gehört oder eine `Private Shared` Object-Variablen zum Schützen von Daten, die alle Instanzen gemeinsam.  
  
 Verwenden Sie nicht die `Me` Schlüsselwort ermöglichen eine Sperre für die Instanz Objektdaten. Wenn Code außerhalb der Klasse einen Verweis auf eine Instanz der Klasse enthält, konnte es diesen Verweis verwenden, als ein Sperrobjekt für die für eine `SyncLock` Block ganz anderen von Ihnen, unterschiedliche Daten schützen. Auf diese Weise Ihre Klasse und die andere Klasse können einander blockieren Ausführung ihrer unabhängigen `SyncLock` blockiert. Auf ähnliche Weise Sperren für eine Zeichenfolge kann problematisch werden, da es sich bei jedem anderen Code in den Prozess über die gleiche Zeichenfolge dieselbe Sperre freigibt.  
  
 Verwenden Sie zudem nicht die `Me.GetType` freigegebene Methode, um ein Sperrobjekt für die für bereitzustellen. Grund hierfür ist, `GetType` gibt immer die gleiche `Type` Objekt für einen bestimmten Klassennamen. Externer Code Aufrufen `GetType` für Ihre Klasse und erhalten dasselbe Sperrobjekt, das Sie verwenden. Dies würde die beiden Klassen blockieren miteinander aus ihren `SyncLock` blockiert.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel zeigt eine Klasse, die eine einfache Liste von Nachrichten verwaltet. Es enthält die Nachrichten in einem Array und das letzte Element des Arrays in einer Variablen verwendet. Die `addAnotherMessage` erhöht das letzte Element und speichert die neue Nachricht. Diese beiden Vorgänge werden geschützt, indem die `SyncLock` und `End SyncLock` -Anweisungen, denn sobald das letzte Element erhöht wurde, die neue Nachricht gespeichert werden muss vor dem ein anderen Threads das letzte Element erneut inkrementieren kann.  
  
 Wenn die `simpleMessageList` Klasse eine Liste von Nachrichten zwischen alle zugehörigen Instanzen, die Variablen freigegebener `messagesList` und `messagesLast` deklariert werden als `Shared`. In diesem Fall wird die Variable `messagesLock` muss auch `Shared`, sodass gäbe es ein einzelnes Lock-Objekt, das von jeder Instanz verwendet.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Beispiel wird die Threads und `SyncLock`. Solange die `SyncLock` Anweisung vorhanden ist, der Anweisungsblock eines kritischen Abschnitts und `balance` wird nie eine negative Zahl. Können Sie Auskommentieren der `SyncLock` und `End SyncLock` Anweisungen, die Auswirkungen der eingepasst finden Sie unter der `SyncLock` Schlüsselwort.  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### <a name="comments"></a>Kommentare  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading>  
 <xref:System.Threading.Monitor>  
 [Threadsynchronisierung](../../programming-guide/concepts/threading/thread-synchronization.md)  
 [Threading](../../programming-guide/concepts/threading/index.md)
