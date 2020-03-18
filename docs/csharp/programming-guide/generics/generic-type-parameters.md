---
title: Generische Typparameter – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 8412980d35989c445d2e0a44c0b9f35e6087bb8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712181"
---
# <a name="generic-type-parameters-c-programming-guide"></a>Generische Typparameter (C#-Programmierhandbuch)

Bei der Definition eines generischen Typs oder einer Methode ist ein Typparameter ein Platzhalter für einen bestimmten Typ, den ein Client angibt, wenn eine Instanz des generischen Typs erstellt wird. Eine generische Klasse, z.B. die unter `GenericList<T>`Einführung in Generics[ aufgelistete Klasse ](./index.md), kann nicht ohne Anpassung verwendet werden, denn sie ist nicht wirklich ein Typ, sondern mehr wie die Kopie eines Typs. Um `GenericList<T>` verwenden zu können, muss der Clientcode einen konstruierten Typ deklarieren und instanziieren, indem er ein Typargument in spitzen Klammern angibt. Das Typargument für diese spezielle Klasse kann jeder Typ sein, der vom Compiler erkannt wird. Instanzen von konstruierten Typen können in beliebiger Zahl erstellt werden, wobei jede Instanz ein anderes Typargument verwendet, z.B.:  
  
[!code-csharp[csProgGuideGenerics#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#7)]  
  
Bei jeder dieser Instanzen von `GenericList<T>` wird jedes Vorkommen von `T` in der Klasse zur Laufzeit durch das Typargument ersetzt. Aufgrund dieser Ersetzung werden drei separate typsichere und effiziente Objekte mithilfe einer einzigen Klassendefinition erstellt. Weitere Informationen dazu, wie diese Ersetzung von der CLR ausgeführt wird, finden Sie unter [Generics zur Laufzeit](./generics-in-the-run-time.md).  
  
## <a name="type-parameter-naming-guidelines"></a>Richtlinien für die Benennung von Typparametern  
  
- **Verwenden** Sie zur Benennung von generischen Typparametern beschreibende Namen, es sei denn, ein Name aus einem einzelnen Buchstaben reicht als Erklärung völlig aus, und ein beschreibender Name würde das Verständnis für den Namen nicht wirklich erhöhen.  
  
   [!code-csharp[csProgGuideGenerics#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#8)]  
  
- **Verwenden** Sie T als Typparametername für Typen, die einen einzelnen Buchstaben als Typparameter haben.  
  
   [!code-csharp[csProgGuideGenerics#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#9)]  
  
- **Verwenden** Sie das Präfix „T“ für beschreibende Typparameternamen.  
  
   [!code-csharp[csProgGuideGenerics#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#10)]  
  
- **Überlegen** Sie, ob Sie Einschränkungen, die für einen Typparameter gelten, im Namen des Parameters angeben möchten. Ein auf `ISession` eingeschränkter Parameter könnte z.B. `TSession` genannt werden.

Die Codeanalyseregel [CA1715](/visualstudio/code-quality/ca1715) kann verwendet werden, um sicherzustellen, dass Typparameter entsprechend benannt werden.
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Collections.Generic>
- [C#-Programmierhandbuch](../index.md)
- [Generics](./index.md)
- [Unterschiede zwischen C++-Vorlagen und C#-Generics](./differences-between-cpp-templates-and-csharp-generics.md)
