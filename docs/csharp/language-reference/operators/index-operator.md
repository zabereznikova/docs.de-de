---
title: '[]-Operator (C#-Referenz) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '[]_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4eaecd5cd70c396a62856087a7b37f38e02d2383
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-c-reference"></a>Operator [] (C#-Referenz)
Eckige Klammern (`[]`) werden für Arrays, Indexer und Attribute verwendet. Sie können auch mit Zeigern verwendet werden.  
  
## <a name="remarks"></a>Hinweise  
 Auf einen Arraytyp folgt `[]`:  
  
 [!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 Um auf ein Element eines Arrays zuzugreifen, wird der Index des gewünschten Elements in Klammern eingeschlossen:  
  
 [!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 Eine Ausnahme wird ausgelöst, wenn ein Arrayindex außerhalb des gültigen Bereichs liegt.  
  
 Der Arrayindizierungsoperator kann nicht überladen werden. Allerdings können Typen Indexer definieren sowie Eigenschaften, die einen oder mehrere Parameter annehmen. Indexerparameter werden wie Arrayindizes in rechteckige Klammern eingeschlossen, können aber als beliebiger Typ deklariert werden, während Arrayindizes ganzzahlig sein müssen.  
  
 .NET Framework definiert z.B. einen `Hashtable`-Typ, der Schlüssel und Werte beliebigen Typs verknüpft:  
  
 [!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 Rechteckigen Klammern werden auch zum Angeben von [Attributen](../../../csharp/programming-guide/concepts/attributes/index.md) verwendet:  
  
 [!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 Sie können rechteckige Klammern verwenden, um einen Zeiger zu referenzieren:  
  
 [!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 Es wird keine Überprüfung der Begrenzungen durchgeführt.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)   
 [Indexer](../../../csharp/programming-guide/indexers/index.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)

