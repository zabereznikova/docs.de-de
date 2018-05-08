---
title: Beschränkungen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: 57378c3aa18a5cc108c10e8654e55803f3cf9052
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="visual-basic-limitations"></a>Beschränkungen in Visual Basic
Frühere Versionen von Visual Basic erzwungen Grenzen in Code, z. B. die Länge der Variablennamen, die Anzahl der Variablen in Modulen und Modulgröße zulässig. In Visual Basic .NET und wurden diese Einschränkungen gelockert wurde und Sie haben mehr Freiheit beim Schreiben und Einfügen von Code.  
  
 Physische Grenzen sind mehr auf die Laufzeit Arbeitsspeicher als Zeitpunkt der Kompilierung Leistungsaspekten abhängig. Wenn Sie angemessen Programmierstile verwenden und große Anwendungen in mehrere Klassen und Module unterteilen, ist sehr geringer Wahrscheinlichkeit eine interne Visual Basic-Beschränkung.  
  
 Es folgen einige Einschränkungen, die Sie in extremen Fällen auftreten:  
  
-   **Länge des Namens.** Es wird eine maximale Anzahl von Zeichen für den Namen jedes deklarierten Programmierelements. Dieser Maximalwert gilt für eine gesamte Qualifizierungspfad auf, wenn der Elementname qualifiziert wird. Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Zeilenlänge.** Es gibt ein Maximum von 65535 Zeichen in eine physische Zeile des Quellcodes. Die logische Quellcodezeile kann mehr Zeit, wenn Sie das Zeilenfortsetzungszeichen verwenden. Finden Sie unter [wie: umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Dimensionen des Arrays.** Es wird eine maximale Anzahl von Dimensionen, die Sie für ein Array zu deklarieren. Dies schränkt wie viele Indizes, die Sie verwenden können, um ein Arrayelement anzugeben. Finden Sie unter [Dimensionen in Visual Basic-Array](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Länge der Zeichenfolge.** Es wird eine maximale Anzahl von Unicode-Zeichen, die in einer einzelnen Zeichenfolge gespeichert werden können. Finden Sie unter [Zeichenfolgendatentyp](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Umgebung String-length-Funktion.** Es ist ein Maximum von 32768 Zeichen für eine beliebige Umgebungszeichenfolge als Befehlszeilenargument verwendet. Dies ist eine Einschränkung auf allen Plattformen.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
