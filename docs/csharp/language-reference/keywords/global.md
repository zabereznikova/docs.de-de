---
title: Kontextabhängiges Schlüsselwort „global“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
ms.openlocfilehash: 837245e31a9a795aa2f13cfc6c33fefb6402801d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2018
ms.locfileid: "44217451"
---
# <a name="global-c-reference"></a><span data-ttu-id="22b67-102">global (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="22b67-102">global (C# Reference)</span></span>

<span data-ttu-id="22b67-103">Wenn das Kontextschlüsselwort `global` dem [Operator „::“](../operators/namespace-alias-qualifer.md) vorangestellt ist, verweist es auf den globalen Namespace. Dabei handelt es sich um den Standardnamespace für alle C#-Programme, der ansonsten unbenannt ist.</span><span class="sxs-lookup"><span data-stu-id="22b67-103">The `global` contextual keyword, when it comes before the [:: operator](../operators/namespace-alias-qualifer.md), refers to the global namespace, which is the default namespace for any C# program and is otherwise unnamed.</span></span> <span data-ttu-id="22b67-104">Weitere Informationen finden Sie unter [How to: Use the Global Namespace Alias (Vorgehensweise: Verwenden des globalen Namespacealias)](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span><span class="sxs-lookup"><span data-stu-id="22b67-104">For more information, see [How to: Use the Global Namespace Alias](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span></span>

## <a name="example"></a><span data-ttu-id="22b67-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22b67-105">Example</span></span>

<span data-ttu-id="22b67-106">Im folgenden Beispiel wird veranschaulicht, wie mit dem Kontextschlüsselwort `global` angegeben wird, dass die Klasse `TestApp` im globalen Namespace definiert ist:</span><span class="sxs-lookup"><span data-stu-id="22b67-106">The following example shows how to use the `global` contextual keyword to specify that the class `TestApp` is defined in the global namespace:</span></span>

[!code-csharp[csrefKeywordsContextual#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#13)]

## <a name="see-also"></a><span data-ttu-id="22b67-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22b67-107">See also</span></span>

- [<span data-ttu-id="22b67-108">Namespaces</span><span class="sxs-lookup"><span data-stu-id="22b67-108">Namespaces</span></span>](../../programming-guide/namespaces/index.md)