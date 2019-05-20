---
title: Zeigervergleich – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: 25bc1c7b701c36d2daf1918986eb6a8e56980990
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635135"
---
# <a name="pointer-comparison-c-programming-guide"></a>Zeigervergleich (C#-Programmierhandbuch)
Sie können die folgenden Operatoren zum Vergleichen von Zeigern jeglichen Typs anwenden:  
  
 **==   !=   \<   >   \<=   >=**  
  
 Die Vergleichsoperatoren vergleichen die Adressen der zwei Operanden, als handle es sich bei diesen um ganze Zahlen ohne Vorzeichen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuidePointers#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#16)]  
  
 [!code-csharp[csProgGuidePointers#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#17)]  
  
## <a name="sample-output"></a>Beispielausgabe  
 `True`  
  
 `False`  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
- [Bearbeiten von Zeigern](../../../csharp/programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
- [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Typen](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
