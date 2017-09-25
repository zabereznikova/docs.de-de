---
title: operator (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- operator_CSharpKeyword
- operator
dev_langs:
- CSharp
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
caps.latest.revision: 19
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
ms.openlocfilehash: 76d403493861e9c587672412cd2989c419b8717a
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="operator-c-reference"></a>operator (C#-Referenz)
Verwenden Sie das Schlüsselwort `operator`, um einen integrierten Operator zu überladen oder um eine benutzerdefinierte Konvertierung in einer Klassen- oder Strukturdeklaration bereitzustellen.  
  
## <a name="example"></a>Beispiel  
 Die Folgende ist eine stark vereinfachte Klasse für Bruchzahlen. Sie überlädt die Operatoren „+“ und „*“, um Addition und Multiplikation bei Brüchen auszuführen, und stellt auch einen Konvertierungsoperator bereit, der einen Bruchtyp in einen doppelten Typ konvertiert.  
  
 [!code-cs[csrefKeywordsConversion#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/operator_1.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [implicit](../../../csharp/language-reference/keywords/implicit.md)   
 [explicit](../../../csharp/language-reference/keywords/explicit.md)   
 [Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

