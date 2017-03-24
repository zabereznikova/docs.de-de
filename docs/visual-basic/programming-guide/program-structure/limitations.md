---
title: "Beschränkungen in Visual Basic | Microsoft-Dokumentation"
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
- limits
- limitations, Visual Basic
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: d556b045b4ebae6ba24c0571a6cb7e5337c6a8f2
ms.lasthandoff: 03/13/2017

---
# <a name="visual-basic-limitations"></a>Beschränkungen in Visual Basic
Frühere Versionen von [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erzwungen Grenzen in Code, z. B. die Länge der Namen von Variablen, die zulässige Anzahl von Variablen in Modulen und Modulgröße. In [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], wurden haben diese Einschränkungen gelockert, was Ihnen mehr Freiheit beim Schreiben und Anordnen von Code.  
  
 Physische Grenzen hängen eher auf die Laufzeit Arbeitsspeicher als Gesichtspunkten während der Kompilierung. Wenn Sie angemessen Programmierverfahren verwenden und teilen Sie umfangreiche in mehrere Klassen und Module, es ist sehr geringe Chance, beim Auftreten eines internen [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Einschränkung.  
  
 Es folgen einige Einschränkungen, die in extremen Fällen auftreten:  
  
-   **Länge des Namens.** Es gibt eine maximale Anzahl von Zeichen für den Namen jedes deklarierten Programmierelements. Dieser Maximalwert gilt für eine gesamte Qualifizierungspfad, wenn der Elementname qualifiziert wird. Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   **Zeilenlänge.** Es ist maximal 65.535 Zeichen in eine physikalische Zeile von Quellcode. Die logische Quellcodezeile kann länger, wenn Sie das Zeilenfortsetzungszeichen verwenden. Finden Sie unter [wie: umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).  
  
-   **Dimensionen des Arrays.** Es wird eine maximale Anzahl von Dimensionen, die Sie für ein Array deklarieren können. Auf diese Weise wie viele Indizes, die Sie verwenden können, auf ein Arrayelement angeben. Finden Sie unter [Array-Dimensionen in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).  
  
-   **Länge der Zeichenfolge.** Es gibt eine maximale Anzahl von Unicode-Zeichen, die in einer einzelnen Zeichenfolge gespeichert werden können. Finden Sie unter [String-Datentyp](../../../visual-basic/language-reference/data-types/string-data-type.md).  
  
-   **Zeichenfolgenlänge Umgebung.** Es gibt ein Maximum von Umgebungszeichenfolgen als Befehlszeilenargument verwendet 32768 Zeichen. Dies ist eine Einschränkung auf allen Plattformen.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Visual Basic-Benennungskonventionen](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
