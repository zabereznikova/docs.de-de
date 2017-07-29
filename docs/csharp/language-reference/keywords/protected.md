---
title: protected (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- protected
- protected_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- protected keyword [C#]
ms.assetid: 05ce3794-6675-4025-bddb-eaaa0ec22892
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c3d24389f66edec313d4f5238b0aee02518e33b7
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="protected-c-reference"></a>protected (C#-Referenz)
Das `protected`-Schlüsselwort ist ein Zugriffsmodifizierer für Member. Auf einen geschützten Member kann innerhalb seiner Klasse und von Instanzen abgeleiteter Klasse zugegriffen werden. Einen Vergleich von `protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md).  
  
## <a name="example"></a>Beispiel  
 Auf einen geschützten Member einer Basisklasse kann in einer abgeleiteten Klasse zugegriffen werden, nur wenn der Zugriff über den Typ der abgeleiteten Klasse erfolgt. Sehen Sie sich z.B. folgenden Codeabschnitt an:  
  
 [!code-cs[csrefKeywordsModifiers#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_1.cs)]  
  
 Die Anweisung `a.x = 10` generiert einen Fehler, da sie innerhalb der statischen Main-Methode erstellt wird und keine Instanz der Klasse B ist.  
  
 Strukturmember können nicht geschützt werden, da die Struktur nicht vererbt werden kann.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die `DerivedPoint`-Klasse von `Point` abgeleitet. Daher können Sie direkt von der abgeleiteten Klasse auf die geschützten Member der Basisklasse zugreifen.  
  
 [!code-cs[csrefKeywordsModifiers#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/protected_2.cs)]  
  
 Wenn Sie die Zugriffsebenen von `x` und `y` auf [private](../../../csharp/language-reference/keywords/private.md) ändern, wird der Compiler die Fehlermeldungen anzeigen:  
  
 `'Point.y' is inaccessible due to its protection level.`  
  
 `'Point.x' is inaccessible due to its protection level.`  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Zugriffsebenen](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [Public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)

