---
title: namespace-Schlüsselwort (C#-Programmierreferenz)
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: 2cdc1e33d86dae675411b571e553b467e5c1f891
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856425"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="ad97c-102">Namespace (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ad97c-102">namespace (C# Reference)</span></span>

<span data-ttu-id="ad97c-103">Das `namespace`-Schlüsselwort wird verwendet, um einen Gültigkeitsbereich zu deklarieren, der eine Gruppe von verwandten Objekten enthält.</span><span class="sxs-lookup"><span data-stu-id="ad97c-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="ad97c-104">Sie können einen Namespace verwenden, um Codeelemente zu organisieren und global eindeutige Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ad97c-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="ad97c-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad97c-105">Remarks</span></span>

<span data-ttu-id="ad97c-106">Innerhalb eines Namespace können Sie 0 (null) oder mehr der folgenden Typen deklarieren:</span><span class="sxs-lookup"><span data-stu-id="ad97c-106">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="ad97c-107">einen anderen Namespace</span><span class="sxs-lookup"><span data-stu-id="ad97c-107">another namespace</span></span>

- [<span data-ttu-id="ad97c-108">class</span><span class="sxs-lookup"><span data-stu-id="ad97c-108">class</span></span>](class.md)

- [<span data-ttu-id="ad97c-109">interface</span><span class="sxs-lookup"><span data-stu-id="ad97c-109">interface</span></span>](interface.md)

- [<span data-ttu-id="ad97c-110">struct</span><span class="sxs-lookup"><span data-stu-id="ad97c-110">struct</span></span>](struct.md)

- [<span data-ttu-id="ad97c-111">enum</span><span class="sxs-lookup"><span data-stu-id="ad97c-111">enum</span></span>](enum.md)

- [<span data-ttu-id="ad97c-112">delegate</span><span class="sxs-lookup"><span data-stu-id="ad97c-112">delegate</span></span>](delegate.md)

<span data-ttu-id="ad97c-113">Unabhängig davon, ob Sie einen Namespace in einer C#-Quelldatei explizit deklarieren, fügt der Compiler einen Standardnamespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="ad97c-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="ad97c-114">Dieser unbenannte Namespace, der manchmal auch als der globale Namespace bezeichnet wird, ist in jeder Datei vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ad97c-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="ad97c-115">Jeder Bezeichner im globalen Namespace ist für die Verwendung in einem benannten Namespace verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ad97c-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="ad97c-116">Namespaces verfügen implizit über öffentlichen Zugriff, und dies kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ad97c-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="ad97c-117">Eine Erläuterung der Zugriffsmodifizierer, die Sie einem Element in einem Namespace zuweisen können, finden Sie unter [Zugriffsmodifizierer](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="ad97c-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="ad97c-118">Es ist möglich, einen Namespace in zwei oder mehr Deklarationen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ad97c-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="ad97c-119">Im folgenden Beispiel werden beispielsweise zwei Klassen als Teil des `MyCompany`-Namespace definiert:</span><span class="sxs-lookup"><span data-stu-id="ad97c-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="ad97c-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad97c-120">Example</span></span>

<span data-ttu-id="ad97c-121">Im folgenden Beispiel wird veranschaulicht, wie eine statische Methode in einem geschachtelten Namespace aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ad97c-121">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a><span data-ttu-id="ad97c-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad97c-122">Related resources</span></span>

<span data-ttu-id="ad97c-123">Weitere Informationen zur Verwendung von Namespaces finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ad97c-123">For more information about using namespaces, see the following topics:</span></span>

- [<span data-ttu-id="ad97c-124">Namespaces</span><span class="sxs-lookup"><span data-stu-id="ad97c-124">Namespaces</span></span>](../../programming-guide/namespaces/index.md)

- [<span data-ttu-id="ad97c-125">Using-Namespaces</span><span class="sxs-lookup"><span data-stu-id="ad97c-125">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)

- [<span data-ttu-id="ad97c-126">Gewusst wie: Verwenden des globalen Namespacealias</span><span class="sxs-lookup"><span data-stu-id="ad97c-126">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="ad97c-127">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="ad97c-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ad97c-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad97c-128">See also</span></span>

- [<span data-ttu-id="ad97c-129">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ad97c-129">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="ad97c-130">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ad97c-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ad97c-131">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ad97c-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ad97c-132">Namespaceschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ad97c-132">Namespace Keywords</span></span>](namespace-keywords.md)
- [<span data-ttu-id="ad97c-133">using</span><span class="sxs-lookup"><span data-stu-id="ad97c-133">using</span></span>](using.md)