---
title: "Versionsverwaltung mit den Schl&#252;sselw&#246;rtern &quot;override&quot; und &quot;new&quot; (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, override und new"
  - "C#-Sprache, Versionskontrolle"
ms.assetid: 88247d07-bd0d-49e9-a619-45ccbbfdf0c5
caps.latest.revision: 25
caps.handback.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Versionsverwaltung mit den Schl&#252;sselw&#246;rtern &quot;override&quot; und &quot;new&quot; (C#-Programmierhandbuch)
Die Programmiersprache C\# ist so ausgelegt, dass die Versionen von [Basis](../../../csharp/language-reference/keywords/base.md)\-Klassen und abgeleiteten Klassen in unterschiedlichen Bibliotheken weiterentwickelt werden können, wobei die Rückwärtskompatibilität erhalten bleibt.  Daher wird z. B. die Einführung eines neuen Members in einer Basis\-[Klasse](../../../csharp/language-reference/keywords/class.md), der denselben Namen wie ein Member in einer abgeleiteten Klasse hat, vollständig durch C\# unterstützt und führt nicht zu unerwartetem Verhalten.  Dies bedeutet auch, dass in einer Klasse explizit angegeben werden muss, ob eine Methode eine geerbte Methode überschreiben soll oder ob es sich um eine neue Methode handelt, hinter der sich eine geerbte Methode mit ähnlichem Namen verbirgt.  
  
 In C\# können abgeleitete Klassen Methoden mit dem gleichen Namen wie Basisklassenmethoden enthalten.  
  
-   Die Basisklassenmethode muss als [virtual](../../../csharp/language-reference/keywords/virtual.md) definiert werden.  
  
-   Wenn vor der Methode in der abgeleiteten Klasse weder das [new](../../../csharp/language-reference/keywords/new.md)\-Schlüsselwort noch das [override](../../../csharp/language-reference/keywords/override.md)\-Schlüsselwort stehen, gibt der Compiler eine Warnung aus. Die Methode wird dann behandelt, als wäre das `new`\-Schlüsselwort vorhanden.  
  
-   Falls vor der Methode in der abgeleiteten Klasse das `new`\-Schlüsselwort steht, wird die Methode als unabhängig von der Methode in der Basisklasse definiert.  
  
-   Falls vor der Methode in der abgeleiteten Klasse das `override`\-Schlüsselwort steht, rufen Objekte der abgeleiteten Klasse diese Methode anstatt der Basisklassenmethode auf.  
  
-   Die Basisklassenmethode kann aus der abgeleiteten Klasse mit dem `base`\-Schlüsselwort aufgerufen werden.  
  
-   Die Schlüsselwörter `override`, `virtual` und `new` können auch auf Eigenschaften, Indexer und Ereignisse angewendet werden.  
  
 C\#\-Methoden sind standardmäßig nicht virtuell.  Wenn eine Methode als virtuell deklariert ist, kann jede Klasse, die die Methode erbt, ihre eigene Version implementieren.  Um aus einer Methode eine virtuelle Methode zu machen, wird der `virtual`\-Modifizierer in der Methodendeklaration der Basisklasse verwendet.  Anschließend kann die virtuelle Methode der Basisklasse von der abgeleiteten Klasse mit dem `override`\-Schlüsselwort überschrieben werden oder mit dem `new`\-Schlüsselwort in der Basisklasse verborgen werden.  Wenn weder das `override`\-Schlüsselwort noch das `new`\-Schlüsselwort angegeben ist, gibt der Compiler eine Warnung aus, und die Basisklassenmethode wird von der Methode in der abgeleiteten Klasse verborgen.  
  
 Um dies praktisch zu demonstrieren, nehmen Sie einmal an, dass die Firma A eine Klasse mit dem Namen `GraphicsClass` erstellt hat, die von Ihrem Programm verwendet wird.  `GraphicsClass` sieht folgendermaßen aus:  
  
 [!code-cs[csProgGuideInheritance#27](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-overrid_1.cs)]  
  
 Sie verwenden diese Klasse, um eine eigene Klasse abzuleiten, und fügen eine neue Methode hinzu:  
  
 [!code-cs[csProgGuideInheritance#28](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-overrid_2.cs)]  
  
 Die Anwendung funktioniert ohne Probleme, bis Firma A eine neue Version von `GraphicsClass` herausgibt, die dem folgenden Code ähnelt:  
  
 [!code-cs[csProgGuideInheritance#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-overrid_3.cs)]  
  
 Die neue Version von `GraphicsClass` enthält jetzt eine Methode mit dem Namen `DrawRectangle`.  Anfänglich geschieht nichts.  Die neue Version ist mit der alten immer noch binärkompatibel.  Jede von Ihnen eingesetzte Software arbeitet weiter, auch wenn die neue Klasse auf diesen Computersystemen installiert wird.  Aufrufe der Methode `DrawRectangle` verweisen weiterhin auf die Version in der abgeleiteten Klasse.  
  
 Sobald Sie jedoch die Anwendung mit der neuen Version von `GraphicsClass` erneut kompilieren, wird vom Compiler die Warnung CS0108 ausgegeben.  Diese Warnung informiert Sie, dass Sie entscheiden müssen, wie sich die `DrawRectangle`\-Methode in der Anwendung verhalten soll.  
  
 Wenn die Methode die neue Basisklassenmethode überschreiben soll, verwenden Sie das `override`\-Schlüsselwort:  
  
 [!code-cs[csProgGuideInheritance#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-overrid_4.cs)]  
  
 Das `override`\-Schlüsselwort stellt sicher, dass alle von `YourDerivedGraphicsClass` abgeleiteten Objekte die abgeleitete Klassenversion von `DrawRectangle` verwenden.  Von `YourDerivedGraphicsClass` abgeleitete Objekte können weiterhin mit dem Basisschlüsselwort auf die Basisklassenversion von `DrawRectangle` zugreifen:  
  
 [!code-cs[csProgGuideInheritance#44](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-overrid_5.cs)]  
  
 Wenn die Methode die neue Basisklassenmethode nicht überschreiben soll, müssen Sie die folgenden Aspekte berücksichtigen:  Um Verwechslungen zwischen den beiden Methoden zu vermeiden, können Sie die Methode umbenennen.  Dies kann zeitaufwändig und fehleranfällig sein und ist für einige Fälle einfach ungeeignet.  Wenn das Projekt relativ klein ist, können Sie die Methode allerdings mithilfe der Umgestaltungsoptionen von Visual Studio umbenennen.  Weitere Informationen finden Sie unter [Refactoring Classes and Types \(Class Designer\)](/visual-studio/ide/refactoring-classes-and-types-class-designer).  
  
 Alternativ können Sie die Warnung mit dem `new`\-Schlüsselwort in der Definition der abgeleiteten Klasse umgehen:  
  
 [!code-cs[csProgGuideInheritance#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-overrid_6.cs)]  
  
 Das `new`\-Schlüsselwort teilt dem Compiler mit, dass die in der Basisklasse enthaltene Definition durch Ihre Definition verborgen wird.  Dies ist das Standardverhalten.  
  
## Überschreiben und Methodenauswahl  
 Wenn eine Methode von einer Klasse benannt wird, wählt der C\#\-Compiler die am besten geeignete Aufrufmethode, falls mehr als eine Methode mit dem Aufruf kompatibel ist. Dies ist z. B. der Fall bei zwei Methoden mit demselben Namen und Parametern, die mit den übergebenen Parametern übereinstimmen.  Die folgenden Methoden wären kompatibel:  
  
 [!code-cs[csProgGuideInheritance#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-overrid_7.cs)]  
  
 Wenn `DoWork` in einer Instanz von `Derived` aufgerufen wird, versucht der C\#\-Compiler zuerst den Aufruf mit den Versionen von `DoWork` kompatibel zu machen, die ursprünglich auf `Derived` deklariert wurden.  Überschreibungsmethoden werden nicht als Klassendeklarationen betrachtet, sondern als neue Implementierungen einer Methode, die in einer Basisklasse deklariert ist.  Nur wenn der C\#\-Compiler für den Methodenaufruf keine übereinstimmende ursprüngliche Methode auf `Derived` finden kann, versucht er, den Aufruf an eine überschriebene Methode zu richten, die den gleichen Namen und kompatible Parameter hat.  Beispiele:  
  
 [!code-cs[csProgGuideInheritance#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-overrid_8.cs)]  
  
 Da die Variable `val` implizit in double konvertiert werden kann, ruft der C\#\-Compiler `DoWork(double)` statt `DoWork(int)` auf.  Es gibt zwei Möglichkeiten, dies zu vermeiden.  Zum einen sollten Sie vermeiden, neue Methoden mit dem gleichen Namen wie virtuelle Methoden zu deklarieren.  Zum anderen können Sie den C\#\-Compiler anweisen, die virtuelle Methode aufzurufen. Dazu muss die Instanz von `Derived` in `Base` umgewandelt werden, um dann die die Methodenliste der Basisklasse durchsuchen zu können.  Da die Methode virtuell ist, wird die Implementierung von `DoWork(int)` für `Derived` aufgerufen.  Beispiele:  
  
 [!code-cs[csProgGuideInheritance#34](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-overrid_9.cs)]  
  
 Weitere Beispiele für `new` und `override`, finden Sie [Wann müssen die Schlüsselwörter "override" und "new" verwendet werden?](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)weitere Informationen.  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md)