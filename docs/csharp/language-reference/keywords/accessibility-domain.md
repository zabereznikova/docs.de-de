---
title: Zugriffsdomäne – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- accessibility domain [C#]
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
ms.openlocfilehash: 814aa8d3965674abe8bdb60b738cbeff93701ceb
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606140"
---
# <a name="accessibility-domain-c-reference"></a>Zugriffsdomäne (C#-Referenz)
Die Zugriffsdomäne eines Members gibt an, in welche Teile des Programms ein Member verwiesen werden kann. Wenn der Member in einem anderen Typ geschachtelt ist, wird seine Zugriffsdomäne sowohl durch das [Zugriffslevel](./accessibility-levels.md) des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt.  
  
 Die Zugriffsdomäne eines Typs der obersten Ebene ist mindestens der Programmtext des Projekts, in dem er deklariert ist. Das bedeutet, dass die Domäne alle Quelldateien des Projekts enthält. Die Zugriffsdomäne eines geschachtelten Typs ist mindestens der Programmtext des Typs, in dem er deklariert ist. Das bedeutet, dass die Domäne der Typkörper ist, der alle geschachtelten Typen enthält. Die Zugriffsdomäne eines geschachtelten Typs geht nie über die des enthaltenden Typs hinaus. Diese Konzepte werden im folgenden Beispiel dargestellt.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel enthält einen Typ der obersten Ebene `T1`, und zwei geschachtelte Klassen `M1` und `M2`. Die Klassen enthalten Felder mit unterschiedlichen deklarierten Zugriffen. In der `Main`-Methode folgt jeder Anweisung ein Kommentar, der die Zugriffsdomäne jedes Members angibt. Beachten Sie, dass die Anweisungen, die versuchen, auf die Member zu verweisen, auf die nicht zugegriffen werden kann, auskommentiert werden. Wenn Sie die Compilerfehler anzeigen möchten, die durch Verweisen auf einen Member verursacht werden, auf den nicht zugegriffen werden kann, entfernen Sie die Kommentare nacheinander.  
  
[!code-csharp[csrefKeywordsModifiers#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#4)]
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](./index.md)
- [Zugriffsmodifizierer](./access-modifiers.md)
- [Zugriffsebenen](./accessibility-levels.md)
- [Einschränkungen bei der Verwendung von Zugriffsebenen](./restrictions-on-using-accessibility-levels.md)
- [Zugriffsmodifizierer](../../programming-guide/classes-and-structs/access-modifiers.md)
- [public](./public.md)
- [private](./private.md)
- [protected](./protected.md)
- [internal](./internal.md)
