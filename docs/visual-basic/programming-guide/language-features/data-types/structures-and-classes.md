---
title: Strukturen und Klassen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures
- classes [Visual Basic]
- structures, compared to classes
- structures, structure variables
- structure variables
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e7402ec0fcfc279470d39a4919d3b5ec8b5d9dff
ms.lasthandoff: 03/13/2017

---
# <a name="structures-and-classes-visual-basic"></a>Strukturen und Klassen (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Die Syntax für Strukturen und Klassen, mit dem Ergebnis, dass größtenteils die gleichen Funktionen unterstützen vereinheitlicht. Es gibt jedoch auch wichtige Unterschiede zwischen Strukturen und Klassen.  
  
 Klassen haben den Vorteil, Verweistypen – Übergabe eines Verweises ist effizienter als die Übergabe einer Strukturvariablen mit allen zugehörigen Daten. Auf der anderen Seite erfordern Strukturen keine Zuordnung von Arbeitsspeicher auf dem globalen Heap.  
  
 Da Sie von einer Struktur geerbt werden können, sollten Strukturen nur für Objekte verwendet werden, die nicht erweitert werden müssen. Verwenden Sie Strukturen, wenn das Objekt, das Sie erstellen möchten, hat eine Größe von kleinen Instanz und die Leistungsmerkmale von Klassen und Strukturen berücksichtigen.  
  
## <a name="similarities"></a>Ähnlichkeit  
 Strukturen und Klassen sind ähnlich wie in folgender Hinsicht:  
  
-   Beide sind *Container* Typen, d. h., dass sie andere Typen als Member enthalten.  
  
-   Beide verfügen über Member, die Konstruktoren, Methoden, Eigenschaften, Felder, Konstanten, Enumerationen, Ereignisse und Ereignishandler enthalten können. Verwechseln Sie jedoch nicht diese Member mit dem deklarierten *Elemente* einer Struktur.  
  
-   Die Member beider können Zugriffsebenen aufweisen. Beispielsweise kann ein Member deklariert werden `Public` und anderen `Private`.  
  
-   Beide können Schnittstellen implementieren.  
  
-   Beide können freigegebene Konstruktoren mit oder ohne Parameter verfügen.  
  
-   Beide verfügbar machen, können eine *Standardeigenschaft*, vorausgesetzt, dass die Eigenschaft nimmt mindestens einen Parameter.  
  
-   Beide können deklarieren und Auslösen von Ereignissen, und beide können Delegaten deklarieren.  
  
## <a name="differences"></a>Unterschiede  
 Strukturen und Klassen unterscheiden sich in den folgenden Angaben:  
  
-   Strukturen sind *Werttypen*; Klassen sind *Verweistypen*. Eine Variable eines Strukturtyps enthält die Struktur Daten, anstatt mit einem Verweis auf die Daten als Typ einer Klasse ist.  
  
-   Strukturen verwenden stapelzuordnung. Klassen verwenden Heapzuweisung.  
  
-   Alle Strukturelemente sind `Public` standardmäßig-Klasse Variablen und Konstanten sind `Private` , während andere Klassenmember sind standardmäßig `Public` standardmäßig. Dieses Verhalten für Klassenmember bietet Kompatibilität mit dem Visual Basic 6.0-System Standardwerte.  
  
-   Eine Struktur müssen mindestens eine nicht freigegebene Variable oder weder freigegebenes noch benutzerdefiniertes Ereigniselement. eine Klasse kann völlig leer sein.  
  
-   Strukturelemente nicht deklariert werden, als `Protected`; Klassenmember können.  
  
-   Eine Strukturprozedur kann Ereignisse behandeln, nur, wenn es eine [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` Verfahren und nur von der [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md); jede Klassenprozedur kann Ereignisse entweder behandeln die [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) Schlüsselwort oder `AddHandler` Anweisung. Weitere Informationen finden Sie unter [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md).  
  
-   Struktur Variablendeklarationen können keine Initialisierer oder Anfangsgröße für Arrays angeben; Klasse Variablendeklarationen können.  
  
-   Strukturen erben implizit von der <xref:System.ValueType?displayProperty=fullName>-Klasse und nicht von einem anderen Typ; erben Klassen können von einer Klasse oder einer anderen <xref:System.ValueType?displayProperty=fullName>.</xref:System.ValueType?displayProperty=fullName> Klassen erben</xref:System.ValueType?displayProperty=fullName>  
  
-   Strukturen können nicht vererbt werden; Klassen sind.  
  
-   Strukturen werden nie beendet, sodass die common Language Runtime (CLR) aufgerufen werden, nie die <xref:System.Object.Finalize%2A>-Methode für eine Struktur; Klassen werden vom Garbage Collector (GC), der aufgerufen wird, beendet <xref:System.Object.Finalize%2A>für eine Klasse, wenn es erkennt keine aktiven Verweise mehr vorhanden sind.</xref:System.Object.Finalize%2A> </xref:System.Object.Finalize%2A>  
  
-   Eine Struktur ist einen Konstruktor nicht erforderlich. eine Klasse ist.  
  
-   Strukturen können nicht freigegebene Konstruktoren nur, wenn sie Parameter annehmen; Klassen können sie mit oder ohne Parameter aufweisen.  
  
 Jede Struktur verfügt über einen impliziten öffentlichen Konstruktor ohne Parameter. Dieser Konstruktor initialisiert alle die Datenmember der Struktur mit ihren Standardwerten. Sie können dieses Verhalten nicht neu definieren.  
  
## <a name="instances-and-variables"></a>Instanzen und Variablen  
 Da Strukturen Werttypen sind, wird Strukturvariablen permanent an eine einzelne Strukturinstanz gebunden. Jedoch sind Klassen Verweistypen, und eine Objektvariable kann zu unterschiedlichen Zeitpunkten auf unterschiedliche Klasseninstanzen verweisen. Dieser Unterschied wirkt sich auf folgende Weise auf die Verwendung von Strukturen und Klassen aus:  
  
-   **Die Initialisierung.** Eine Strukturvariable umfasst implizit eine Initialisierung der Elemente mithilfe des parameterlosen Konstruktors der Struktur. Aus diesem Grund `Dim s As struct1` entspricht `Dim s As struct1 = New struct1()`.  
  
-   **Zuweisen von Variablen.** Wenn Sie eine Strukturvariable zu einem anderen zuweisen oder eine Strukturinstanz an Prozedurarguments übergeben, werden die aktuellen Werte aller Variablenelemente in die neue Struktur kopiert. Wenn Sie eine Objektvariable zu einem anderen zuweisen oder eine Objektvariable an eine Prozedur übergeben, wird nur der Verweiszeiger kopiert.  
  
-   **Zuweisen von Nothing.** Weisen Sie den Wert [nichts](../../../../visual-basic/language-reference/nothing.md) auf eine Struktur Variable, aber die Instanz weiterhin der Variablen zugeordnet werden. Weiterhin können Sie ihre Methoden aufrufen und die Datenelemente zugreifen, obwohl die Variablenelemente durch die Zuweisung erneut initialisiert werden.  
  
     Im Gegensatz dazu, wenn Sie eine Objektvariablen auf `Nothing`, heben Sie die Zuweisung von allen Klasseninstanzen und Sie können nicht auf Member über die Variable zugreifen, bis Sie eine andere Instanz zuweisen.  
  
-   **Mehrere Instanzen.** Eine Objektvariablen kann verschiedene Klasseninstanzen zu unterschiedlichen Zeiten zugewiesen, und verschiedene Objektvariablen können gleichzeitig auf die gleiche Klasseninstanz verweisen. Vorgenommenen Änderungen auf die Werte von Klassenmembern Einfluss auf die Elemente, die beim Zugriff über eine andere Variable, die auf dieselbe Instanz verweisen.  
  
     Strukturelemente sind hingegen in ihrer eigenen Instanz isoliert. Ändert die Werte werden nicht widergespiegelt, in anderen Strukturvariablen, auch in anderen Instanzen des gleichen `Structure` Deklaration.  
  
-   **Gleichheit.** Gleichheitstest zwei Strukturen muss für ein Element für Element durchgeführt werden. Zwei Objektvariablen können verglichen werden, mithilfe der <xref:System.Object.Equals%2A>-Methode.</xref:System.Object.Equals%2A> <xref:System.Object.Equals%2A>Gibt an, ob die zwei Variablen auf dieselbe Instanz verweisen.</xref:System.Object.Equals%2A>  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Strukturen und andere Programmierelemente](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)   
 [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
