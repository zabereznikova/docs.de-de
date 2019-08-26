---
title: Kontextabhängiges by-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- by
- by_CSharpKeyword
helpviewer_keywords:
- by keyword [C#]
ms.assetid: efe6f0e3-be40-4df2-a144-c7db968ae052
ms.openlocfilehash: 23daf2aaf5d9456c76c5b2ac889243b1ed31b077
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602223"
---
# <a name="by-c-reference"></a><span data-ttu-id="7ea49-102">by (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7ea49-102">by (C# Reference)</span></span>

<span data-ttu-id="7ea49-103">Das Kontextschlüsselwort `by` wird in der `group`-Klausel in einem Abfrageausdruck verwendet, um anzugeben, wie die zurückgegebenen Elemente gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7ea49-103">The `by` contextual keyword is used in the `group` clause in a query expression to specify how the returned items should be grouped.</span></span> <span data-ttu-id="7ea49-104">Weitere Informationen finden Sie unter [group-Klausel](./group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="7ea49-104">For more information, see [group clause](./group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="7ea49-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7ea49-105">Example</span></span>

<span data-ttu-id="7ea49-106">Im folgenden Beispiel wird gezeigt, wie das Kontextschlüsselwort `by` in einer `group`-Klausel verwendet wird, um anzugeben, dass die Kursteilnehmer anhand des ersten Buchstaben des Nachnamens gruppiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7ea49-106">The following example shows the use of the `by` contextual keyword in a `group` clause to specify that the students should be grouped according to the first letter of the last name of each student.</span></span>

[!code-csharp[csrefKeywordsContextual#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#10)]

## <a name="see-also"></a><span data-ttu-id="7ea49-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ea49-107">See also</span></span>

- [<span data-ttu-id="7ea49-108">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="7ea49-108">LINQ Query Expressions</span></span>](../../programming-guide/linq-query-expressions/index.md)
