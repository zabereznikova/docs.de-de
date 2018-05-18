---
title: Generische Typparameter (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 35029b90fb7b905a87055596cf8dcd6a84ef9d36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="generic-type-parameters-c-programming-guide"></a>Generische Typparameter (C#-Programmierhandbuch)
Bei der Definition eines generischen Typs oder einer Methode ist ein Typparameter ein Platzhalter für einen bestimmten Typ, den ein Client angibt, wenn eine Variable des generischen Typs instanziiert wird. Eine generische Klasse, z.B. die unter [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md) aufgelistete Klasse `GenericList<T>`, kann nicht ohne Anpassung verwendet werden, denn sie ist nicht wirklich ein Typ, sondern mehr wie die Kopie eines Typs. Um `GenericList<T>` verwenden zu können, muss der Clientcode einen konstruierten Typ deklarieren und instanziieren, indem er ein Typargument in spitzen Klammern angibt. Das Typargument für diese spezielle Klasse kann jeder Typ sein, der vom Compiler erkannt wird. Instanzen von konstruierten Typen können in beliebiger Zahl erstellt werden, wobei jede Instanz ein anderes Typargument verwendet, z.B.:  
  
 [!code-csharp[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]  
  
 Bei jeder dieser Instanzen von `GenericList<T>` wird jedes Vorkommen von `T` in der Klasse zur Laufzeit durch das Typargument ersetzt. Aufgrund dieser Ersetzung werden drei separate typsichere und effiziente Objekte mithilfe einer einzigen Klassendefinition erstellt. Weitere Informationen dazu, wie diese Ersetzung von der CLR ausgeführt wird, finden Sie unter [Generika zur Laufzeit](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
## <a name="type-parameter-naming-guidelines"></a>Richtlinien für die Benennung von Typparametern  
  
-   **Verwenden** Sie zur Benennung von generischen Typparametern beschreibende Namen, es sei denn, ein Name aus einem einzelnen Buchstaben reicht als Erklärung völlig aus, und ein beschreibender Name würde das Verständnis für den Namen nicht wirklich erhöhen.  
  
     [!code-csharp[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]  
  
-   **Verwenden** Sie T als Typparametername für Typen, die einen einzelnen Buchstaben als Typparameter haben.  
  
     [!code-csharp[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]  
  
-   **Verwenden** Sie das Präfix „T“ für beschreibende Typparameternamen.  
  
     [!code-csharp[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]  
  
-   **Überlegen** Sie, ob Sie Einschränkungen, die für einen Typparameter gelten, im Namen des Parameters angeben möchten. Ein auf `ISession` eingeschränkter Parameter könnte z.B. `TSession` genannt werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic>  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Generika](../../../csharp/programming-guide/generics/index.md)  
 [Unterschiede zwischen C++-Vorlagen und C#-Generika](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)
