---
title: Einschränkungen
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: abe4acd5850aa6065bf4f6fd41bc610ede7ad13f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097955"
---
# <a name="visual-basic-limitations"></a>Beschränkungen in Visual Basic

Frühere Versionen von Visual Basic erzwungene Grenzen im Code, wie z. b. die Länge der Variablennamen, die Anzahl der zulässigen Variablen in Modulen und die Modulgröße. In Visual Basic .net wurden diese Einschränkungen gelockert, sodass Sie mehr Freiheit beim Schreiben und anordnen Ihres Codes haben.  
  
 Die physischen Grenzwerte sind mehr für den Lauf Zeit Arbeitsspeicher als bei Überlegungen zur Kompilierzeit voneinander abhängig. Wenn Sie vorsichtige Programmierverfahren verwenden und große Anwendungen in mehrere Klassen und Module aufteilen, besteht die Wahrscheinlichkeit, dass eine interne Visual Basic Einschränkung auftritt.  
  
 Im folgenden finden Sie einige Einschränkungen, die in Extremfällen auftreten können:  
  
- **Länge des Namens.** Es gibt eine maximale Anzahl von Zeichen für den Namen aller deklarierten Programmier Elemente. Dieser Höchstwert gilt für eine gesamte Qualifikations Zeichenfolge, wenn der Elementname qualifiziert ist. Siehe [Declared Element Names](../language-features/declared-elements/declared-element-names.md).  
  
- **Zeilenlänge.** In einer physischen Zeile des Quellcodes sind maximal 65535 Zeichen enthalten. Die logische Quell Code Zeile kann länger sein, wenn Sie Zeilen Fortsetzungs Zeichen verwenden. Siehe Gewusst [wie: unterbrechen und Kombinieren von Anweisungen im Code](how-to-break-and-combine-statements-in-code.md)  
  
- **Array Dimensionen.** Es gibt eine maximale Anzahl von Dimensionen, die Sie für ein Array deklarieren können. Dies schränkt die Anzahl der Indizes ein, die Sie verwenden können, um ein Array Element anzugeben. Weitere Informationen finden Sie [unter Array Dimensionen in Visual Basic](../language-features/arrays/array-dimensions.md).  
  
- **Zeichen folgen Länge.** Es gibt eine maximale Anzahl von Unicode-Zeichen, die Sie in einer einzelnen Zeichenfolge speichern können. Siehe [String-Datentyp](../../language-reference/data-types/string-data-type.md).  
  
- **Länge der Umgebungs Zeichenfolge.** Für jede Umgebungs Zeichenfolge, die als Befehlszeilenargument verwendet wird, sind maximal 32768 Zeichen zulässig. Dies ist eine Einschränkung auf allen Plattformen.  
  
## <a name="see-also"></a>Siehe auch

- [Programmstruktur und Codekonventionen](program-structure-and-code-conventions.md)
- [Benennungskonventionen in Visual Basic](naming-conventions.md)
