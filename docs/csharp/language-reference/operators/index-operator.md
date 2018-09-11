---
title: Operator [] (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 19283a795f8cfc444dfcb186dcecc0ea86eb27fd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467431"
---
# <a name="-operator-c-reference"></a>Operator [] (C#-Referenz)
Eckige Klammern (`[]`) werden für Arrays, Indexer und Attribute verwendet. Sie können auch mit Zeigern verwendet werden.  
  
## <a name="remarks"></a>Hinweise  
 Auf einen Arraytyp folgt `[]`:  
  
 [!code-csharp[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 Um auf ein Element eines Arrays zuzugreifen, wird der Index des gewünschten Elements in Klammern eingeschlossen:  
  
 [!code-csharp[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 Eine Ausnahme wird ausgelöst, wenn ein Arrayindex außerhalb des gültigen Bereichs liegt.  
  
 Der Arrayindizierungsoperator kann nicht überladen werden. Allerdings können Typen Indexer definieren, die einen oder mehrere Parameter annehmen. Indexerparameter werden wie Arrayindizes in rechteckige Klammern eingeschlossen, können aber als beliebiger Typ deklariert werden, während Arrayindizes ganzzahlig sein müssen.  
  
 .NET Framework definiert z.B. einen `Hashtable`-Typ, der Schlüssel und Werte beliebigen Typs verknüpft:  
  
 [!code-csharp[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 Rechteckigen Klammern werden auch zum Angeben von [Attributen](../../../csharp/programming-guide/concepts/attributes/index.md) verwendet:  
  
 [!code-csharp[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 Sie können rechteckige Klammern verwenden, um einen Zeiger zu referenzieren:  
  
 [!code-csharp[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 Es wird keine Überprüfung der Begrenzungen durchgeführt.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)  
- [Arrays](../../../csharp/programming-guide/arrays/index.md)  
- [Indexer](../../../csharp/programming-guide/indexers/index.md)  
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
- [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)
