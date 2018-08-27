---
title: partial (Methode) (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 69e16dd8b0fe0055124aca90fea65a36d9e413f3
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933684"
---
# <a name="partial-method-c-reference"></a>partial (Methode) (C#-Referenz)
Bei partiellen Methoden wird die Signatur in einem Teil eines partiellen Typs definiert, und die Implementierung wird in einem anderen Teil des Typs definiert. Mit partiellen Methoden können Klassen-Designer Methoden-Hooks bereitstellen, die Ereignis-Handlern ähneln und die Entwickler ggf. implementieren können. Wenn der Entwickler keine Implementierung angibt, entfernt der Compiler die Signatur bei der Kompilierung. Die folgenden Bedingungen gelten für partielle Methoden:  
  
-   Die Signaturen in beiden Teilen des partiellen Typs müssen übereinstimmen.  
  
-   Die Methode muss "void" zurückgeben.  
  
-   Es sind keine Zugriffsmodifizierer zulässig. Partielle Methoden sind implizit privat.  
  
 Im folgenden Beispiel wird eine partielle Methode veranschaulicht, die in zwei Teilen einer partiellen Klasse definiert ist:  
  
 [!code-csharp[csrefKeywordsContextual#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-method_1.cs)]  
  
 Weitere Informationen finden Sie unter [Partielle Klassen und Methoden](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [partial (Typ)](../../../csharp/language-reference/keywords/partial-type.md)
