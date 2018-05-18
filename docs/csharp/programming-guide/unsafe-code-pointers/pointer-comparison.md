---
title: Zeigervergleich (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: af264cd1572faafe25ee170b35cbeb48ed0fb2aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="pointer-comparison-c-programming-guide"></a>Zeigervergleich (C#-Programmierhandbuch)
Sie können die folgenden Operatoren zum Vergleichen von Zeigern jeglichen Typs anwenden:  
  
 **==   !=   \<   >   \<=   >=**  
  
 Die Vergleichsoperatoren vergleichen die Adressen der zwei Operanden, als handle es sich bei diesen um ganze Zahlen ohne Vorzeichen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a>Beispielausgabe  
 `True`  
  
 `False`  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)  
 [Bearbeiten von Zeigern](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Typen](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
