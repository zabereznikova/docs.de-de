---
title: Generische Typparameter – C#-Programmierhandbuch
description: Erfahren Sie mehr über die Definition von generischen Typen in C#, wo ein Typparameter ein Platzhalter für einen Typ ist, den ein Client für eine Instanz des generischen Typs angibt.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: dc37029378ac1e9ec194d95b561787761d69a9fd
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299252"
---
# <a name="generic-type-parameters-c-programming-guide"></a>Generische Typparameter (C#-Programmierhandbuch)

Bei der Definition eines generischen Typs oder einer Methode ist ein Typparameter ein Platzhalter für einen bestimmten Typ, den ein Client angibt, wenn eine Instanz des generischen Typs erstellt wird. Eine generische Klasse, z.B. die unter [Einführung in Generics](./index.md) aufgelistete Klasse `GenericList<T>`, kann nicht ohne Anpassung verwendet werden, denn sie ist nicht wirklich ein Typ, sondern mehr wie die Kopie eines Typs. Um `GenericList<T>` verwenden zu können, muss der Clientcode einen konstruierten Typ deklarieren und instanziieren, indem er ein Typargument in spitzen Klammern angibt. Das Typargument für diese spezielle Klasse kann jeder Typ sein, der vom Compiler erkannt wird. Instanzen von konstruierten Typen können in beliebiger Zahl erstellt werden, wobei jede Instanz ein anderes Typargument verwendet, z.B.:  
  
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
