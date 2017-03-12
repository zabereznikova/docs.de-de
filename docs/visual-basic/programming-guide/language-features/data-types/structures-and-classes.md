---
title: "Structures and Classes (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "classes [Visual Basic], vs. structures"
  - "structures"
  - "classes [Visual Basic]"
  - "structures, compared to classes"
  - "structures, structure variables"
  - "structure variables"
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Structures and Classes (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] wird die Syntax für Strukturen und Klassen vereinheitlicht, mit dem Ergebnis, dass Strukturen und Klassen größtenteils die gleichen Funktionen unterstützen.  Zwischen Klassen und Strukturen bestehen jedoch auch wichtige Unterschiede.  
  
 Klassen haben den Vorteil, Verweistypen zu sein — die Übergabe eines Verweises ist effizienter als die Übergabe einer Strukturvariablen mit allen zugehörigen Daten.  Dagegen muss für Strukturen kein Speicher des globalen Heaps belegt werden.  
  
 Da nicht von einer Struktur geerbt werden kann, dürfen Strukturen nur für Objekte verwendet werden, die nicht erweitert werden müssen.  Verwenden Sie Strukturen, wenn die Instanz des zu erstellenden Objekts klein ist. Ziehen Sie außerdem die Leistungsmerkmale von Klassen im Vergleich zu Strukturen in Betracht.  
  
## Ähnlichkeiten  
 Strukturen und Klassen sind sich in folgender Hinsicht ähnlich:  
  
-   Beide sind *Containertypen*, d. h. sie enthalten andere Typen als Member.  
  
-   Beide besitzen Member, z. B. Konstruktoren, Methoden, Eigenschaften, Felder, Konstanten, Enumerationen, Ereignisse und Ereignishandler.  Diese Member dürfen jedoch nicht mit den deklarierten *Elementen* einer Struktur verwechselt werden.  
  
-   Die Member beider Typen können individuelle Zugriffsebenen aufweisen.  Beispielsweise kann ein Member als `Public` und ein anderer als `Private` deklariert sein.  
  
-   Beide können Schnittstellen implementieren.  
  
-   Beide können freigegebene Konstruktoren mit oder ohne Parameter besitzen.  
  
-   Beide können eine *Standardeigenschaft* verfügbar machen, vorausgesetzt, dieser Eigenschaft wird mindestens ein Parameter übergeben.  
  
-   Beide können Ereignisse deklarieren und auslösen, und beide können Delegaten deklarieren.  
  
## Unterschiede  
 Zwischen Strukturen und Klassen bestehen folgende Unterschiede:  
  
-   Strukturen sind *Werttypen*. Klassen sind *Verweistypen*.  Im Unterschied zu einer Variablen eines Klassentyps enthält eine Variable eines Strukturtyps die Daten dieser Struktur statt eines Verweises auf die Daten.  
  
-   Strukturen verwenden Stapelzuweisung; Klassen verwenden Heapzuweisung.  
  
-   Alle Strukturelemente sind standardmäßig `Public`; Klassenvariablen und Konstanten sind standardmäßig `Private`, während andere Klassenmember standardmäßig `Public` sind.  Aufgrund dieses Verhaltens sind Klassenmember mit den Standardelementen des Visual Basic 6.0\-Systems kompatibel.  
  
-   Eine Struktur muss mindestens eine nicht freigegebene Variable oder ein nicht freigegebenes und nicht benutzerdefiniertes Ereigniselement enthalten. Eine Klasse kann völlig leer sein.  
  
-   Strukturelemente können im Gegensatz zu Klassenmembern nicht als `Protected` deklariert werden.  
  
-   Eine Strukturprozedur kann nur dann Ereignisse behandeln, wenn sie als [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub`\-Prozedur definiert ist und die [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md)\-Anweisung zur Ereignisbehandlung verwendet wird. Jede Klassenprozedur kann mithilfe des [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md)\-Schlüsselworts oder der `AddHandler`\-Anweisung Ereignisse behandeln.  Weitere Informationen finden Sie unter [Events](../../../../visual-basic/programming-guide/language-features/events/events.md).  
  
-   In Strukturvariablendeklarationen können keine Initialisierungen oder anfängliche Arraygrößen angegeben werden, in Deklarationen von Klassenvariablen ist dies hingegen möglich.  
  
-   Strukturen erben implizit von der <xref:System.ValueType?displayProperty=fullName>\-Klasse und können von keinem anderen Typ erben. Klassen können von einer beliebigen Klasse bzw. von beliebigen Klassen, ausgenommen <xref:System.ValueType?displayProperty=fullName>, erben.  
  
-   Strukturen können nicht geerbt werden, Klassen hingegen schon.  
  
-   Strukturen werden nie beendet, sodass die Common Language Runtime \(CLR\) nie die <xref:System.Object.Finalize%2A>\-Methode für eine Struktur aufruft. Klassen werden durch den Garbage Collector \(GC\) beendet, der <xref:System.Object.Finalize%2A> für eine Klasse aufruft, wenn er feststellt, dass keine aktiven Verweise mehr vorhanden sind.  
  
-   Eine Struktur erfordert keinen Konstruktor, eine Klasse hingegen schon.  
  
-   Strukturen können nur dann über nicht gemeinsame Konstruktoren verfügen, wenn sie Parameter annehmen; bei Klassen ist dies mit oder ohne Parameter möglich.  
  
 Jede Struktur verfügt über einen impliziten öffentlichen Konstruktor ohne Parameter.  Dieser Konstruktor initialisiert alle Datenmember der Struktur mit ihren Standardwerten.  Dafür kann kein anderes Verhalten definiert werden.  
  
## Instanzen und Variablen  
 Da es sich bei Strukturen um Werttypen handelt, sind Strukturvariablen immer permanent an eine einzelne Strukturinstanz gebunden.  Klassen sind hingegen Verweistypen, und eine Objektvariable kann zu verschiedenen Zeitpunkten auf unterschiedliche Klasseninstanzen verweisen.  Dieser Unterschied wirkt sich in folgender Weise auf die Verwendung von Strukturen und Klassen aus:  
  
-   **Initialisierung.** Eine Strukturvariable umfasst implizit eine Initialisierung der Elemente mithilfe des parameterlosen Konstruktors der Struktur.  Daher ist `Dim s As struct1` gleichbedeutend mit `Dim s As struct1 = New struct1()`.  
  
-   **Zuweisen von Variablen.** Wenn Sie eine Strukturvariable einer anderen Strukturvariablen zuweisen oder eine Strukturinstanz an ein Prozedurargument übergeben, werden die aktuellen Werte aller Variablenelemente in die neue Struktur kopiert.  Wenn Sie eine Objektvariable einer anderen Objektvariablen zuweisen oder eine Objektvariable an eine Prozedur übergeben, wird nur der Verweiszeiger kopiert.  
  
-   **Zuweisen von Nothing.** Sie können einer Strukturvariablen den Wert [Nothing](../../../../visual-basic/language-reference/nothing.md) zuweisen, jedoch bleibt die Instanz weiterhin der Variablen zugeordnet.  Obwohl die Variablenelemente durch die Zuweisung neu initialisiert werden, können Sie die Methoden der Instanz aufrufen und auf die Datenelemente zugreifen.  
  
     Wenn Sie im Gegensatz dazu eine Objektvariable `Nothing` zuweisen, heben Sie die Zuweisung von allen Klasseninstanzen auf, und Sie können erst wieder über die Variable auf Member zugreifen, wenn Sie eine andere Instanz zuweisen.  
  
-   **Mehrere Instanzen.** Einer Objektvariablen können zu unterschiedlichen Zeitpunkten verschiedene Klasseninstanzen zugewiesen sein, und verschiedene Objektvariablen können gleichzeitig auf dieselbe Klasseninstanz verweisen.  Beim Zugriff über eine andere Variable, die auf dieselbe Instanz zeigt, wirken sich Änderungen an den Werten von Klassenmembern auf diese Member aus.  
  
     Strukturelemente sind hingegen in ihrer eigenen Instanz isoliert.  Änderungen an den Werten werden nicht in anderen Strukturvariablen oder gar in anderen Instanzen derselben `Structure`\-Deklaration wiedergegeben.  
  
-   **Gleichheit.** Ein Gleichheitstest zweier Strukturen muss für jedes einzelne Element durchgeführt werden.  Zwei Objektvariablen können mit der <xref:System.Object.Equals%2A>\-Methode verglichen werden.  <xref:System.Object.Equals%2A> gibt an, ob die zwei Variablen auf die gleiche Instanz zeigen.  
  
## Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Structures and Other Programming Elements](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)   
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)