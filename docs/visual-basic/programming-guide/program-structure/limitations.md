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
ms.openlocfilehash: 0f356b52304110299ed0af9bbccd5d03893f31a9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596357"
---
# <a name="visual-basic-limitations"></a>Beschränkungen in Visual Basic
Frühere Versionen von Visual Basic erzwungen Grenzen in Code, z. B. die Länge der Namen von Variablen, die Anzahl der Variablen in Modulen und Modulgröße zulässig. In Visual Basic .NET haben diese Einschränkungen gelockert wurden Ihnen nur größere freiheiten beim Schreiben und Anordnen von Ihrem Code.  
  
 Physische Grenzen sind mehr auf die Laufzeit Arbeitsspeicher als auf Kompilierzeit-Überlegungen abhängig. Wenn Sie angemessen Programmierverfahren, und Teilen große Anwendungen in mehreren Klassen und Module, ist sehr wenig Aussicht auf eine interne Visual Basic-Begrenzung auftreten.  
  
 Im folgenden sind einige Einschränkungen, die Sie in extremen Fällen auftreten:  
  
-   **Länge des Namens.** Es ist eine maximale Anzahl von Zeichen für den Namen des jede deklariertes Programmierelement ein Element aus. Dieser Höchstwert gilt für eine gesamte Qualifizierungspfad auf, wenn der Elementname qualifiziert wird. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Zeilenlänge.** Es gibt höchstens 65535 Zeichen in einer physischen Zeile des Quellcodes. Die logische Quellcodezeile möglich länger, wenn Sie das Zeilenfortsetzungszeichen verwenden. Weitere Informationen finden Sie unter [How to: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Dimensionen des Arrays.** Es ist eine maximale Anzahl von Dimensionen, die Sie für ein Array deklarieren können. Dadurch wird beschränkt, wie viele Indizes, die Sie verwenden können, ein Arrayelement angeben. Finden Sie unter [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Länge der Zeichenfolge.** Es ist eine maximale Anzahl von Unicode-Zeichen, die in einer einzelnen Zeichenfolge gespeichert werden können. Finden Sie unter [String-Datentyp](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Zeichenfolgenlänge der Umgebung.** Es gibt höchstens 32768 Zeichen für eine beliebige Umgebungszeichenfolge, die als Befehlszeilenargument verwendet. Dies ist eine Einschränkung auf allen Plattformen.  
  
## <a name="see-also"></a>Siehe auch
- [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
