---
title: Zugriffsdomäne (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 8e6af35ea41f6d062bc2b8ee771a1fac21667462
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207905"
---
# <a name="accessibility-domain-c-reference"></a>Zugriffsdomäne (C#-Referenz)
Die Zugriffsdomäne eines Members gibt an, in welche Teile des Programms ein Member verwiesen werden kann. Wenn der Member in einem anderen Typ geschachtelt ist, wird seine Zugriffsdomäne sowohl durch das [Zugriffslevel](../../../csharp/language-reference/keywords/accessibility-levels.md) des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt.  
  
 Die Zugriffsdomäne eines Typs der obersten Ebene ist mindestens der Programmtext des Projekts, in dem er deklariert ist. Das bedeutet, dass die Domäne alle Quelldateien des Projekts enthält. Die Zugriffsdomäne eines geschachtelten Typs ist mindestens der Programmtext des Typs, in dem er deklariert ist. Das bedeutet, dass die Domäne der Typkörper ist, der alle geschachtelten Typen enthält. Die Zugriffsdomäne eines geschachtelten Typs geht nie über die des enthaltenden Typs hinaus. Diese Konzepte werden im folgenden Beispiel dargestellt.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel enthält einen Typ der obersten Ebene `T1`, und zwei geschachtelte Klassen `M1` und `M2`. Die Klassen enthalten Felder mit unterschiedlichen deklarierten Zugriffen. In der `Main`-Methode folgt jeder Anweisung ein Kommentar, der die Zugriffsdomäne jedes Members angibt. Beachten Sie, dass die Anweisungen, die versuchen, auf die Member zu verweisen, auf die nicht zugegriffen werden kann, auskommentiert werden. Wenn Sie die Compilerfehler anzeigen möchten, die durch Verweisen auf einen Member verursacht werden, auf den nicht zugegriffen werden kann, entfernen Sie die Kommentare nacheinander.  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
 [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [Einschränkungen bei der Verwendung von Zugriffsebenen](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)  
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [public](../../../csharp/language-reference/keywords/public.md)  
 [private](../../../csharp/language-reference/keywords/private.md)  
 [protected](../../../csharp/language-reference/keywords/protected.md)  
 [internal](../../../csharp/language-reference/keywords/internal.md)
