---
title: "SyncLock Statement | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.SyncLock"
  - "SyncLock"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "threading [Visual Basic], locks"
  - "SyncLock statement"
  - "locks, threads"
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# SyncLock Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ruft vor dem Ausführen des Anweisungsblocks eine exklusive Sperre für den Block ab.  
  
## Syntax  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## Teile  
 `lockobject`  
 Erforderlich.  Ausdruck, der einen Objektverweis ergibt.  
  
 `block`  
 Dies ist optional.  Block von Anweisungen, die auszuführen sind, wenn die Sperre erworben wird.  
  
 `End SyncLock`  
 Beendet einen `SyncLock`\-Block.  
  
## Hinweise  
 Die `SyncLock`\-Anweisung stellt sicher, dass mehrere Threads den Anweisungsblock nicht gleichzeitig ausführen.  `SyncLock` verhindert, dass jeder Thread in den Block eintritt, bis dieser von keinem anderen Thread ausgeführt wird.  
  
 In der Regel wird `SyncLock` dazu verwendet, Daten vor der Aktualisierung durch mehrere Threads gleichzeitig zu schützen.  Wenn die Anweisungen, mit denen die Daten bearbeitet werden, ohne Unterbrechung ausgeführt werden sollen, fügen Sie sie in einen `SyncLock`\-Block ein.  
  
 Ein durch eine exklusive Sperre geschützter Anweisungsblock wird gelegentlich als *kritischer Abschnitt* bezeichnet.  
  
## Regeln  
  
-   Verzweigen.  Eine Verzweigung in einen `SyncLock`\-Block ist nicht von außerhalb des Blocks möglich.  
  
-   Wert des Sperrobjekts.  Der Wert von `lockobject` kann nicht `Nothing` sein.  Sie müssen das Sperrobjekt erstellen, bevor Sie es in einer `SyncLock`\-Anweisung verwenden.  
  
     Sie können den Wert von `lockobject` nicht ändern, während ein `SyncLock`\-Block ausgeführt wird.  Der Mechanismus verlangt, dass das Sperrobjekt unverändert bleibt.  
  
-   Sie können den [Rechnen Sie](../../../visual-basic/language-reference/operators/await-operator.md)\-Operator in einem `SyncLock`\-Block nicht verwenden.  
  
## Verhalten  
  
-   Mechanismus.  Wenn ein Thread die `SyncLock`\-Anweisung erreicht, wird der `lockobject`\-Ausdruck ausgewertet und die Ausführung des Threads unterbrochen, bis der Thread eine exklusive Sperre für das durch den Ausdruck zurückgegebene Objekt erwirbt.  Wenn ein anderer Thread die `SyncLock`\-Anweisung erreicht, erwirbt er erst dann eine Sperre, wenn vom ersten Thread die `End SyncLock`\-Anweisung ausgeführt wird.  
  
-   Geschützte Daten.  Wenn es sich bei `lockobject` um eine `Shared`\-Variable handelt, hindert die exklusive Sperre einen Thread in jeder Instanz der Klasse daran, den `SyncLock`\-Block auszuführen, wenn dieser von einem anderen Thread ausgeführt wird.  Damit werden Daten geschützt, die für alle Instanzen freigegeben sind.  
  
     Wenn es sich bei `lockobject` um eine Instanzvariable \(nicht `Shared`\) handelt, hindert die Sperre einen Thread, der in der aktuellen Instanz ausgeführt wird, daran, den `SyncLock`\-Block zur gleichen Zeit wie ein anderer Thread derselben Instanz auszuführen.  Dadurch werden von der einzelnen Instanz verwaltete Daten geschützt.  
  
-   Erwerb und Freigabe.  Ein `SyncLock`\-Block verhält sich wie eine `Try...Finally`\-Konstruktion, bei der der `Try`\-Block eine exklusive Sperre für `lockobject` erwirbt, die schließlich vom `Finally`\-Block wieder aufgehoben wird.  Daher garantiert der `SyncLock`\-Block die Aufhebung der Sperre, unabhängig davon, wie Sie den Block beenden.  Dies gilt sogar im Fall einer nicht behandelten Ausnahme.  
  
-   Framework\-Aufrufe.  Der `SyncLock`\-Block erwirbt die exklusive Sperre und gibt sie frei, indem er die `Enter`\-Methode und die `Exit`\-Methode der `Monitor`\-Klasse im <xref:System.Threading>\-Namespace aufruft.  
  
## Programmierempfehlungen  
 Der `lockobject`\-Ausdruck sollte stets ein Objekt ergeben, das ausschließlich zu der von Ihnen erstellten Klasse gehört.  Sie sollten eine `Private`\-Objektvariable deklarieren, um Daten zu schützen, die zu der aktuellen Instanz gehören, oder eine `Private Shared`\-Objektvariable, um Daten zu schützen, die allen Instanzen gemeinsam sind.  
  
 Sie sollten das `Me`\-Schlüsselwort nicht zur Bereitstellung eines Sperrobjekts für Instanzdaten verwenden.  Wenn Code außerhalb der von Ihnen erstellten Klasse einen Verweis auf eine Instanz dieser Klasse enthält, kann dieser Code den Verweis als Sperrobjekt für einen völlig anderen Block als den von Ihnen erstellten `SyncLock`\-Block verwenden, sodass andere Daten geschützt werden.  Auf diese Weise könnten die von Ihnen erstellte Klasse und die andere Klasse die Ausführung der nicht zusammenhängenden `SyncLock`\-Blöcke gegenseitig verhindern.  Ebenso kann die Sperre einer Zeichenfolge problematisch sein, da in dem Prozess jeder andere Code, der dieselbe Zeichenfolge verwendet, dieselbe Sperre anwendet.  
  
 Außerdem sollten Sie die `Me.GetType`\-Methode nicht zur Bereitstellung eines Sperrobjekts für freigegebene Daten verwenden.  Grund hierfür ist, dass `GetType` stets das gleiche `Type`\-Objekt für einen angegebenen Klassennamen zurückgibt.  Externer Code könnte `GetType` für die von Ihnen erstellte Klasse aufrufen und das gleiche Sperrobjekt erhalten, das Sie verwenden.  Dies würde dazu führen, dass beide Klassen einander durch ihre `SyncLock`\-Blöcke blockieren würden.  
  
## Beispiele  
  
### Description  
 Im folgenden Beispiel wird eine Klasse gezeigt, die eine einfache Liste mit Meldungen verwaltet.  Die Meldungen werden in einem Array abgelegt, und das zuletzt verwendete Element dieses Arrays wird in einer Variablen abgelegt.  Die `addAnotherMessage`\-Prozedur erhöht das letzte Element und speichert die neue Meldung.  Diese beiden Operationen werden durch die `SyncLock`\-Anweisung und die `End SyncLock`\-Anweisung geschützt, denn sobald das letzte Element erhöht wurde, muss die neue Meldung gespeichert werden; erst danach kann das letzte Element von einem anderen Thread erneut erhöht werden.  
  
 Würde die `simpleMessageList`\-Klasse in allen Instanzen nur eine gemeinsame Liste von Meldungen verwenden, würden die `messagesList`\-Variable und die `messagesLast`\-Variable als `Shared` deklariert werden.  In diesem Fall sollte die `messagesLock`\-Variable ebenfalls `Shared` sein, sodass von jeder Instanz ein einziges Sperrobjekt verwendet werden würde.  
  
### Code  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### Description  
 Im folgenden Beispiel werden Threads und `SyncLock` verwendet.  Solange die `SyncLock`\-Anweisung vorhanden ist, stellt der Anweisungsblock einen kritischen Abschnitt dar, und `balance` wird nie eine negative Zahl.  Sie können die Anweisungen `SyncLock` und `End SyncLock` auskommentieren, um die Folgen der Auslassung des `SyncLock`\-Schlüsselworts zu erkennen.  
  
### Code  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### Kommentare  
  
## Siehe auch  
 <xref:System.Threading>   
 <xref:System.Threading.Monitor>   
 [Threadsynchronisierung](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md)   
 [Threading](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)