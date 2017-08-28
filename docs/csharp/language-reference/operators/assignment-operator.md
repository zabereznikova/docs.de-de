---
title: "Operator = (C#-Referenz)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
caps.latest.revision: 14
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
ms.openlocfilehash: e40b2f221717461443a5d0247b3401eb527a7b5a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a>Operator = (C#-Referenz)
Der Zuweisungsoperator (`=`) speichert den Wert seines rechtsseitigen Operanden an dem Speicherort, in der Eigenschaft oder in dem Indexer, der durch seinen linksseitigen Operanden angegeben wird, und gibt den Wert als Ergebnis zurück. Die Operanden müssen demselben Typ angehören, oder der rechtsseitige Operand muss implizit in den Typ des linksseitigen Operanden konvertierbar sein.  
  
## <a name="remarks"></a>Hinweise  
 Der Zuweisungsoperator kann nicht überladen werden. Sie können jedoch implizite Konvertierungsoperatoren für einen Typ definieren, um den Zuweisungsoperator mit dem entsprechenden Typ zu verwenden. Weitere Informationen finden Sie unter [Verwenden von Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)

