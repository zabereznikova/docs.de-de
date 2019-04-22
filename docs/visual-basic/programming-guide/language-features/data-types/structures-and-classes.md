---
title: Strukturen und Klassen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
ms.openlocfilehash: 3635729705520518d4c950f8a79da7d1249285bf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841614"
---
# <a name="structures-and-classes-visual-basic"></a>Strukturen und Klassen (Visual Basic)
Visual Basic wird die Syntax für Strukturen und Klassen, mit dem Ergebnis, dass größtenteils die gleichen Funktionen unterstützen vereinheitlicht. Es gibt jedoch auch wichtige Unterschiede zwischen Klassen und Strukturen.  
  
 Klassen haben den Vorteil, Verweistypen – Übergabe eines Verweises ist effizienter als übergeben eine Strukturvariable mit allen zugehörigen Daten. Auf der anderen Seite erfordern Strukturen keine Zuordnung von Arbeitsspeicher auf dem globalen Heap.  
  
 Da Sie aus einer Struktur geerbt werden können, sollten Strukturen nur für Objekte verwendet werden, die nicht erweitert werden müssen. Verwenden Sie Strukturen, wenn das Objekt, die Sie erstellen möchten eine kleine Instanzgröße hat, und berücksichtigen Sie die Leistungsmerkmale von Klassen und Strukturen.  
  
## <a name="similarities"></a>Ähnlichkeiten  
 Strukturen und Klassen sind ähnlich wie in folgender Hinsicht:  
  
-   Beide sind *Container* Typen, was bedeutet, dass sie andere Typen als Member enthalten.  
  
-   Beide verfügen über Member, die Konstruktoren, Methoden, Eigenschaften, Felder, Konstanten, Enumerationen, Ereignisse und Ereignishandler enthalten können. Allerdings Verwechseln Sie nicht diese Member mit dem deklarierten *Elemente* einer Struktur.  
  
-   Mitglieder von können Zugriffsebenen aufweisen. Beispielsweise kann ein Member deklariert werden `Public` und ein weiteres `Private`.  
  
-   Beide können Schnittstellen implementieren.  
  
-   Beide können freigegebene Konstruktoren, mit oder ohne Parameter verfügen.  
  
-   Beide können verfügbar machen eine *Standardeigenschaft*, vorausgesetzt, dass die Eigenschaft über mindestens einen Parameter akzeptiert.  
  
-   Beide können deklarieren und Auslösen von Ereignissen, und beide können Delegaten deklarieren.  
  
## <a name="differences"></a>Unterschiede  
 Strukturen und Klassen unterscheiden sich in den folgenden Angaben:  
  
-   Strukturen sind *Werttypen*; Klassen sind *Verweistypen*. Eine Variable eines Strukturtyps enthält die Struktur der Daten, anstatt mit einem Verweis auf die Daten als ein Klassentyp ist.  
  
-   Verwenden von Strukturen stapelreservierung; Klassen verwenden Heapzuordnung.  
  
-   Alle Strukturelemente sind `Public` standardmäßig-Klasse Variablen und Konstanten sind `Private` standardmäßig, während andere Klassenmember werden `Public` standardmäßig. Dieses Verhalten für Klassenmember bietet Kompatibilität mit dem Visual Basic 6.0-System von Standardwerten.  
  
-   Eine Struktur müssen mindestens eine nicht freigegebene Variable oder nicht benutzerdefiniertes Ereigniselement enthalten Event-Element; eine Klasse kann vollständig leer sein.  
  
-   Können nicht Strukturelemente deklariert werden, als `Protected`;-Klasse, Elemente zu können.  
  
-   Eine Strukturprozedur nur, wenn sie Ereignisse behandeln eine [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` Prozedur, und nur von der [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md); jede Klassenprozedur kann Behandeln von Ereignissen, die mit entweder der [ Behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) Schlüsselwort oder `AddHandler` Anweisung. Weitere Informationen finden Sie unter [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)definiert sind.  
  
-   Struktur-Variablendeklarationen können keine Initialisierer oder Anfangsgröße für Arrays angeben; Klasse Variablendeklarationen können.  
  
-   Strukturen erben implizit vom die <xref:System.ValueType?displayProperty=nameWithType> Klasse und kann nicht von irgendeinem anderen Typ; erben Klassen können von einer Klasse oder Klassen erben, außer <xref:System.ValueType?displayProperty=nameWithType>.  
  
-   Strukturen können nicht vererbt werden; Klassen sind.  
  
-   Strukturen werden nie beendet, nie aufruft und die common Language Runtime (CLR) die <xref:System.Object.Finalize%2A> Methode für jede Struktur; Klassen werden vom Garbage Collector (GC), die aufruft beendet <xref:System.Object.Finalize%2A> für eine Klasse, wenn er erkennt keine aktiven Verweise vorhanden sind Verbleibende.  
  
-   Eine Struktur ist einen Konstruktor nicht erforderlich; eine Klasse ist.  
  
-   Strukturen aufweisen können nicht freigegebene Konstruktoren, die nur dann, wenn sie Parameter annehmen; Klassen können mit oder ohne Parameter verfügen.  
  
 Jede Struktur verfügt über einen impliziten öffentlichen Konstruktor ohne Parameter. Dieser Konstruktor initialisiert alle der Struktur Datenelemente auf ihre Standardwerte zurück. Sie können dieses Verhalten nicht neu definieren.  
  
## <a name="instances-and-variables"></a>Instanzen und Variablen  
 Da Strukturen Werttypen sind, wird jede Strukturvariable permanent auf eine einzelne Struktur-Instanz gebunden. Jedoch sind Klassen Verweistypen, und eine Objektvariablen auf verschiedenen Klasseninstanzen, zu unterschiedlichen Zeitpunkten verweisen kann. Dieser Unterschied wirkt sich auf die die Nutzung von Strukturen und Klassen gibt folgenden Möglichkeiten:  
  
-   **Die Initialisierung.** Eine Strukturvariable enthält implizit eine Initialisierung der Elemente, die mit der Struktur parameterlosen Konstruktor. Aus diesem Grund `Dim s As struct1` entspricht `Dim s As struct1 = New struct1()`.  
  
-   **Zuweisen von Variablen.** Wenn Sie eine Strukturvariable zu einem anderen zuweisen oder eine Strukturinstanz auf ein Prozedurargument übergeben, werden die aktuellen Werte aller Variablen Elemente in die neue Struktur kopiert. Wenn Sie eine Objektvariable in einen anderen zuweisen oder eine Objektvariablen an eine Prozedur übergeben, wird nur der Verweiszeiger kopiert.  
  
-   **Zuweisen von "Nothing".** Weisen Sie den Wert [nichts](../../../../visual-basic/language-reference/nothing.md) auf eine Struktur Variable, aber die Instanz weiterhin mit der Variablen zugeordnet werden soll. Weiterhin können Sie seine Methoden aufrufen und auf die Datenelemente, zugreifen, obwohl Variable Elemente durch die Zuweisung erneut initialisiert werden.  
  
     Im Gegensatz dazu, wenn Sie eine Objektvariablen auf `Nothing`, heben Sie die Zuweisung von jeder Klasseninstanz, und Sie können keine Mitglieder über die Variable zugreifen, bis Sie eine andere Instanz zuweisen.  
  
-   **Mehrere Instanzen.** Eine Objektvariable kann verschiedene Klasseninstanzen, die zu unterschiedlichen Zeiten zugewiesen haben, und mehrere Objektvariablen können gleichzeitig auf die gleiche Instanz der Klasse verweisen. Mit den Werten von Klassenmembern vorgenommene Änderungen Auswirkungen auf die Elemente, die beim Zugriff über eine andere Variable, die auf dieselbe Instanz verweisen.  
  
     Strukturelemente, sind jedoch in einer eigenen Instanz isoliert. Änderungen an deren Werte werden nicht in anderen Strukturvariablen, sogar in anderen Instanzen der gleichen wiedergegeben `Structure` Deklaration.  
  
-   **Gleichheit.** Gleichheitsüberprüfung von zwei Strukturen muss für ein Element für Element durchgeführt werden. Zwei Objektvariablen verglichen werden können, mit der <xref:System.Object.Equals%2A> Methode. <xref:System.Object.Equals%2A> Gibt an, ob die zwei Variablen auf dieselbe Instanz verweisen.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Strukturen und andere Programmierelemente](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
