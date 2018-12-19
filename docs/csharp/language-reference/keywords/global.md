---
title: Kontextabhängiges global-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
ms.openlocfilehash: b9273feb38b14dce61facc0f59b0890c431b9a7a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240790"
---
# <a name="global-c-reference"></a><span data-ttu-id="02b5d-102">global (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="02b5d-102">global (C# Reference)</span></span>

<span data-ttu-id="02b5d-103">Wenn das Kontextschlüsselwort `global` dem [Operator „::“](../operators/namespace-alias-qualifer.md) vorangestellt ist, verweist es auf den globalen Namespace. Dabei handelt es sich um den Standardnamespace für alle C#-Programme, der ansonsten unbenannt ist.</span><span class="sxs-lookup"><span data-stu-id="02b5d-103">The `global` contextual keyword, when it comes before the [:: operator](../operators/namespace-alias-qualifer.md), refers to the global namespace, which is the default namespace for any C# program and is otherwise unnamed.</span></span> <span data-ttu-id="02b5d-104">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des globalen Namespacealias](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span><span class="sxs-lookup"><span data-stu-id="02b5d-104">For more information, see [How to: Use the Global Namespace Alias](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span></span>

## <a name="example"></a><span data-ttu-id="02b5d-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02b5d-105">Example</span></span>

<span data-ttu-id="02b5d-106">Im folgenden Beispiel wird veranschaulicht, wie mit dem Kontextschlüsselwort `global` angegeben wird, dass die Klasse `TestApp` im globalen Namespace definiert ist:</span><span class="sxs-lookup"><span data-stu-id="02b5d-106">The following example shows how to use the `global` contextual keyword to specify that the class `TestApp` is defined in the global namespace:</span></span>

[!code-csharp[csrefKeywordsContextual#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#13)]

## <a name="see-also"></a><span data-ttu-id="02b5d-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02b5d-107">See also</span></span>

- [<span data-ttu-id="02b5d-108">Namespaces</span><span class="sxs-lookup"><span data-stu-id="02b5d-108">Namespaces</span></span>](../../programming-guide/namespaces/index.md)