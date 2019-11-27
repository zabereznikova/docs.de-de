---
title: Strukturen und Klassen
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
ms.openlocfilehash: 3353935a74bb77fa4a630e706aa425063c7a610a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346331"
---
# <a name="structures-and-classes-visual-basic"></a>Strukturen und Klassen (Visual Basic)
Visual Basic vereinheitlicht die Syntax für Strukturen und Klassen, wobei beide Entitäten den größten Teil der gleichen Funktionen unterstützen. Es gibt jedoch auch wichtige Unterschiede zwischen Strukturen und Klassen.  
  
 Klassen haben den Vorteil, dass Sie Verweis Typen sind – das Übergeben eines Verweises ist effizienter als das Übergeben einer Struktur Variablen mit sämtlichen Daten. Andererseits erfordern Strukturen keine Speicher Belegung auf dem globalen Heap.  
  
 Da Sie nicht von einer Struktur erben können, sollten Strukturen nur für Objekte verwendet werden, die nicht erweitert werden müssen. Verwenden Sie Strukturen, wenn das Objekt, das Sie erstellen möchten, eine kleine instanzgröße hat, und berücksichtigen Sie die Leistungsmerkmale von Klassen im Vergleich zu Strukturen.  
  
## <a name="similarities"></a>Ähnlichkeit  
 Strukturen und Klassen ähneln in den folgenden Punkten:  
  
- Beide sind *Container* Typen. Dies bedeutet, dass Sie andere Typen als Member enthalten.  
  
- Beide verfügen über Member, die Konstruktoren, Methoden, Eigenschaften, Felder, Konstanten, Enumerationen, Ereignisse und Ereignishandler enthalten können. Verwechseln Sie diese Member jedoch nicht mit den deklarierten *Elementen* einer Struktur.  
  
- Mitglieder beider Elemente können über individualisierte Zugriffsebenen verfügen. Beispielsweise kann ein Member `Public` und ein anderer `Private`deklariert werden.  
  
- Beide können Schnittstellen implementieren.  
  
- Beide können gemeinsame Konstruktoren mit oder ohne Parameter aufweisen.  
  
- Beide können eine *Default-Eigenschaft*verfügbar machen, sofern diese Eigenschaft mindestens einen Parameter annimmt.  
  
- Beide können Ereignisse deklarieren und auslassen, und beide können Delegaten deklarieren.  
  
## <a name="differences"></a>Differenz  
 Strukturen und Klassen unterscheiden sich in den folgenden Details:  
  
- Strukturen sind *Werttypen*. Klassen sind *Verweis Typen*. Eine Variable eines Struktur Typs enthält die Daten der Struktur, anstatt einen Verweis auf die Daten als Klassentyp zu enthalten.  
  
- Strukturen verwenden die Stapel Zuordnung. Klassen verwenden Heap Zuordnung.  
  
- Alle Strukturelemente werden standardmäßig `Public`. Klassen Variablen und Konstanten werden standardmäßig `Private`, während andere Klassenmember standardmäßig `Public` werden. Dieses Verhalten für Klassenmember bietet Kompatibilität mit dem Visual Basic 6,0-System der Standardwerte.  
  
- Eine Struktur muss mindestens eine nicht freigegebene Variable oder ein nicht frei gegebenes, Nichtbenutzer definiertes Ereignis Element aufweisen. eine Klasse kann vollständig leer sein.  
  
- Strukturelemente können nicht als `Protected`deklariert werden. Klassenmember können.  
  
- In einer Struktur Prozedur können Ereignisse nur behandelt werden, wenn es sich um eine frei [gegebene](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` Prozedur handelt, die nur über die [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md)verwendet wird. alle Klassen Prozeduren können Ereignisse behandeln, indem Sie entweder das [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) -Schlüsselwort oder die `AddHandler`-Anweisung verwenden. Weitere Informationen finden Sie unter [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
- Struktur Variablen Deklarationen können keine Initialisierer oder anfangs Größen für Arrays angeben. Klassen Variablen Deklarationen können sein.  
  
- Strukturen erben implizit von der <xref:System.ValueType?displayProperty=nameWithType>-Klasse und können nicht von einem anderen Typ erben. Klassen können von einer beliebigen Klasse oder anderen Klassen erben als <xref:System.ValueType?displayProperty=nameWithType>.  
  
- Strukturen können nicht vererbt werden. Klassen sind.  
  
- Strukturen werden nie beendet, sodass die Common Language Runtime (CLR) die <xref:System.Object.Finalize%2A>-Methode niemals für jede Struktur aufruft. Klassen werden vom Garbage Collector (GC) beendet, das <xref:System.Object.Finalize%2A> für eine Klasse aufruft, wenn erkannt wird, dass keine aktiven Verweise vorhanden sind.  
  
- Eine-Struktur erfordert keinen Konstruktor. eine-Klasse.  
  
- Strukturen können nicht freigegebene Konstruktoren haben, wenn Sie Parameter annehmen. Klassen können Sie mit oder ohne Parameter aufweisen.  
  
 Jede Struktur verfügt über einen impliziten öffentlichen Konstruktor ohne Parameter. Dieser Konstruktor initialisiert alle Datenelemente der-Struktur mit ihren Standardwerten. Dieses Verhalten kann nicht neu definiert werden.  
  
## <a name="instances-and-variables"></a>Instanzen und Variablen  
 Da Strukturen Werttypen sind, ist jede Struktur Variable permanent an eine einzelne Struktur Instanz gebunden. Klassen sind jedoch Verweis Typen, und eine Objekt Variable kann zu unterschiedlichen Zeitpunkten auf verschiedene Klassen Instanzen verweisen. Dieser Unterschied wirkt sich auf die Verwendung von Strukturen und Klassen auf folgende Weise aus:  
  
- **Initialisierung.** Eine Struktur Variable schließt implizit eine Initialisierung der Elemente mit dem Parameter losen Konstruktor der Struktur ein. Daher entspricht `Dim s As struct1` `Dim s As struct1 = New struct1()`.  
  
- **Zuweisen von Variablen.** Wenn Sie eine Struktur Variable einem anderen zuweisen oder eine Struktur Instanz an ein Prozedur Argument übergeben, werden die aktuellen Werte aller Variablen Elemente in die neue Struktur kopiert. Wenn Sie eine Objekt Variable einem anderen zuweisen oder eine Objekt Variable an eine Prozedur übergeben, wird nur der Verweis Zeiger kopiert.  
  
- **Zuweisen von nichts.** Sie können einem Struktur Variablen den Wert [Nothing](../../../../visual-basic/language-reference/nothing.md) zuweisen, aber die Instanz wird weiterhin der Variablen zugeordnet. Sie können weiterhin seine Methoden aufrufen und auf dessen Datenelemente zugreifen, obwohl Variablen Elemente von der Zuweisung erneut initialisiert werden.  
  
     Wenn Sie dagegen eine Objekt Variable auf `Nothing`festlegen, wird Sie von einer beliebigen Klasseninstanz getrennt, und Sie können nicht auf Member über die Variable zugreifen, bis Sie Ihr eine andere Instanz zuweisen.  
  
- **Mehrere Instanzen.** Einer Objektvariablen können jeweils unterschiedliche Klassen Instanzen zugewiesen werden, und mehrere Objektvariablen können gleichzeitig auf dieselbe Klasseninstanz verweisen. Änderungen, die Sie an den Werten von Klassenmembern vornehmen, wirken sich auf diese Member aus, wenn Sie über eine andere Variable auf dieselbe Instanz zugreifen  
  
     Strukturelemente sind jedoch innerhalb ihrer eigenen Instanz isoliert. Änderungen an ihren Werten werden in anderen Struktur Variablen nicht widergespiegelt, auch in anderen Instanzen derselben `Structure` Deklaration.  
  
- **Gleichheit.** Gleichheits Tests von zwei-Strukturen müssen mit einem Element-zu-Element-Test ausgeführt werden. Zwei Objektvariablen können mit der <xref:System.Object.Equals%2A>-Methode verglichen werden. <xref:System.Object.Equals%2A> gibt an, ob die beiden Variablen auf dieselbe Instanz verweisen.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Strukturen und andere Programmierelemente](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
