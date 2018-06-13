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
ms.openlocfilehash: e64b54b93463845dd9afd0c0efd0e39f20cab1ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654121"
---
# <a name="structures-and-classes-visual-basic"></a>Strukturen und Klassen (Visual Basic)
Visual Basic wird die Syntax für Strukturen und Klassen, mit dem Ergebnis, dass beide Entitäten größtenteils die gleichen Funktionen unterstützen vereinheitlicht. Es gibt jedoch auch wichtige Unterschiede zwischen Strukturen und Klassen.  
  
 Klassen haben den Vorteil, Verweistypen – Übergabe eines Verweises ist effizienter als übergibt eine Strukturvariable mit allen zugehörigen Daten. Andererseits, erfordern Strukturen keine Zuordnung von Arbeitsspeicher auf dem globalen Heap.  
  
 Da aus einer Struktur geerbt werden kann, sollte Strukturen nur für Objekte verwendet werden, die nicht erweitert werden müssen. Verwenden Sie Strukturen, wenn das Objekt, die Sie erstellen möchten eine kleine Instanzgröße hat, und berücksichtigen Sie die Leistungsmerkmale von Klassen und Strukturen.  
  
## <a name="similarities"></a>Ähnlichkeiten  
 Strukturen und Klassen sind ähnlich wie in folgender Hinsicht:  
  
-   Beide sind *Container* Typen, d. h., dass sie andere Typen als Member enthalten.  
  
-   Beide verfügen über Member, die Konstruktoren, Methoden, Eigenschaften, Felder, Konstanten, Enumerationen, Ereignisse und Ereignishandler enthalten kann. Verwechseln Sie jedoch nicht diese Member mit dem deklarierten *Elemente* einer Struktur.  
  
-   Die Member beider können Zugriffsebenen aufweisen. Beispielsweise kann ein Member deklariert werden `Public` und eine andere `Private`.  
  
-   Beide können Schnittstellen implementieren.  
  
-   Beide können freigegebene Konstruktoren, mit oder ohne Parameter verfügen.  
  
-   Beide können verfügbar machen eine *Standardeigenschaft*, vorausgesetzt, dass die Eigenschaft über mindestens einen Parameter übernimmt.  
  
-   Beide können deklarieren und Auslösen von Ereignissen, und beide können Delegaten deklarieren.  
  
## <a name="differences"></a>Unterschiede  
 Strukturen und Klassen unterscheiden sich in der folgenden Angaben:  
  
-   Strukturen sind *Werttypen*; Klassen sind *Referenztypen*. Eine Variable eines Strukturtyps enthält die Struktur Daten, anstatt mit einem Verweis auf die Daten als ein Klassentyp ist.  
  
-   Strukturen verwenden stapelzuordnung; Verwenden Sie Klassen Heapzuordnung aus.  
  
-   Alle Strukturelemente sind `Public` standardmäßig;-Klasse Variablen und Konstanten sind `Private` während sind von anderen Klassenmembern standardmäßig `Public` standardmäßig. Dieses Verhalten für Klassenmember bietet Kompatibilität mit dem Visual Basic 6.0-System von Standardwerten.  
  
-   Eine Struktur benötigen mindestens eine nicht freigegebene Variable oder weder freigegebenes noch benutzerdefiniertes Event-Element; eine Klasse kann vollständig leer sein.  
  
-   Strukturelemente nicht deklariert werden, als `Protected`; Klassenmember können.  
  
-   Eine Strukturprozedur kann Ereignisse verarbeiten, nur eine [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` Prozedur, und nur mithilfe von der [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md); jede Klassenprozedur kann entweder die mit-Ereignissebehandeln[ Behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) Schlüsselwort oder der `AddHandler` Anweisung. Weitere Informationen finden Sie unter [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
-   Struktur-Variablendeklarationen können keine Initialisierer oder Anfangsgröße für Arrays angeben; Klasse Variablendeklarationen können.  
  
-   Strukturen erben implizit von der <xref:System.ValueType?displayProperty=nameWithType> Klasse und kann nicht von irgendeinem anderen Typ; erben Klassen können nicht von einer Klasse oder Klassen erben <xref:System.ValueType?displayProperty=nameWithType>.  
  
-   Strukturen sind nicht vererbbar; Klassen sind.  
  
-   Strukturen werden nie beendet, damit die common Language Runtime (CLR) aufgerufen werden, nie die <xref:System.Object.Finalize%2A> -Methode für alle Strukturen; Klassen werden vom Garbage Collector (GC), der aufgerufen wird, beendet <xref:System.Object.Finalize%2A> für eine Klasse, wenn er erkennt keine aktiven Verweise vorhanden sind. Verbleibende.  
  
-   Eine Struktur ist einen Konstruktor nicht erforderlich; eine Klasse ist.  
  
-   Strukturen können nicht freigegebene Konstruktoren nur, wenn sie Parameter annehmen; Klassen können sie mit oder ohne Parameter aufweisen.  
  
 Jede Struktur verfügt über einen impliziten öffentlichen Konstruktor ohne Parameter. Dieser Konstruktor initialisiert die Datenelemente für alle der Struktur mit ihren Standardwerten. Sie können dieses Verhalten nicht neu definieren.  
  
## <a name="instances-and-variables"></a>Instanzen und Variablen  
 Da Strukturen Werttypen sind, wird jede Strukturvariable eine einzelne Struktur permanent gebunden. Jedoch Klassen Referenztypen sind, und eine Objektvariable auf verschiedene Klasseninstanzen, zu unterschiedlichen Zeitpunkten verweisen kann. Dieser Unterschied wirkt sich auf folgende Weise auf Ihre Nutzung von Strukturen und Klassen aus:  
  
-   **die Initialisierung.** Eine Strukturvariable umfasst implizit eine Initialisierung der Elemente, die mit der Struktur parameterlosen Konstruktor. Aus diesem Grund `Dim s As struct1` entspricht `Dim s As struct1 = New struct1()`.  
  
-   **Zuweisen von Variablen.** Wenn Sie eine Strukturvariable zu einem anderen zuweisen oder eine Strukturinstanz an eine Prozedur-Argument übergeben, werden die aktuellen Werte aller Variablen Elemente in die neue Struktur kopiert. Wenn Sie eine Objektvariable in einen anderen zuweisen oder eine Objektvariable an eine Prozedur übergeben, wird nur der Verweiszeiger kopiert.  
  
-   **Zuweisen von keine Aktion ausgeführt werden soll.** Weisen Sie den Wert [nichts](../../../../visual-basic/language-reference/nothing.md) auf eine Struktur Variablen, aber die Instanz weiterhin die Variable zugeordnet werden soll. Sie können weiterhin ihre Methoden aufrufen und seine Datenelemente zugreifen, obwohl Variable Elemente durch die Zuweisung erneut initialisiert werden.  
  
     Im Gegensatz dazu, wenn Sie eine Objektvariable auf `Nothing`, heben Sie die Zuweisung von jeder Klasseninstanz, und Sie können keine Member über die Variable zugreifen, bis Sie eine andere Instanz zuweisen.  
  
-   **Mehrere Instanzen.** Eine Objektvariable kann verschiedene Klasseninstanzen zu unterschiedlichen Zeiten zugewiesen haben, und mehrere Objektvariablen können gleichzeitig an dieselbe Klasseninstanz verweisen. Vorgenommenen Änderungen zu den Werten von Klassenmembern Auswirkungen auf diese Member beim Zugriff über eine andere Variable, die auf der gleichen Instanz verweist.  
  
     Strukturelemente sind jedoch in ihrer eigenen Instanz isoliert. Änderungen an ihre Werte werden nicht wiedergegeben, in anderen Strukturvariablen, auch in anderen Instanzen des gleichen `Structure` Deklaration.  
  
-   **Auf Gleichheit.** Gleichheitstests eines der beiden Strukturen muss mit einem Test von Elementen ausgeführt werden. Zwei Objektvariablen können verglichen werden, mithilfe der <xref:System.Object.Equals%2A> Methode. <xref:System.Object.Equals%2A> Gibt an, ob zwei Variablen auf dieselbe Instanz verweisen.  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Strukturen und andere Programmierelemente](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
