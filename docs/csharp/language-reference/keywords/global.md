---
title: Kontextabhängiges Schlüsselwort „global“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
ms.openlocfilehash: 79e0184f58ffc6232038abdd3d9f852147d5732c
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404287"
---
# <a name="global-c-reference"></a><span data-ttu-id="0067c-102">global (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0067c-102">global (C# Reference)</span></span>

<span data-ttu-id="0067c-103">Wenn das Kontextschlüsselwort `global` dem [Operator „::“](../operators/namespace-alias-qualifer.md) vorangestellt ist, verweist es auf den globalen Namespace. Dabei handelt es sich um den Standardnamespace für alle C#-Programme, der ansonsten unbenannt ist.</span><span class="sxs-lookup"><span data-stu-id="0067c-103">The `global` contextual keyword, when it comes before the [:: operator](../operators/namespace-alias-qualifer.md), refers to the global namespace, which is the default namespace for any C# program and is otherwise unnamed.</span></span> <span data-ttu-id="0067c-104">Weitere Informationen finden Sie unter [How to: Use the Global Namespace Alias (Vorgehensweise: Verwenden des globalen Namespacealias)](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span><span class="sxs-lookup"><span data-stu-id="0067c-104">For more information, see [How to: Use the Global Namespace Alias](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span></span>

## <a name="example"></a><span data-ttu-id="0067c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0067c-105">Example</span></span>

<span data-ttu-id="0067c-106">Im folgenden Beispiel wird veranschaulicht, wie mit dem Kontextschlüsselwort `global` angegeben wird, dass die Klasse `TestApp` im globalen Namespace definiert ist:</span><span class="sxs-lookup"><span data-stu-id="0067c-106">The following example shows how to use the `global` contextual keyword to specify that the class `TestApp` is defined in the global namespace:</span></span>

[!code-csharp[csrefKeywordsContextual#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#13)]

## <a name="see-also"></a><span data-ttu-id="0067c-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0067c-107">See also</span></span>

[<span data-ttu-id="0067c-108">Namespaces</span><span class="sxs-lookup"><span data-stu-id="0067c-108">Namespaces</span></span>](../../programming-guide/namespaces/index.md)