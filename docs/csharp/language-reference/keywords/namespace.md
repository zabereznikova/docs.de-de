---
title: namespace-Schlüsselwort – C#-Programmierreferenz
ms.custom: seoapril2019
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: 4859c361b3321c1144204f63896152694f6ac5c9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148758"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="a9e19-102">Namespace (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a9e19-102">namespace (C# Reference)</span></span>

<span data-ttu-id="a9e19-103">Das `namespace`-Schlüsselwort wird verwendet, um einen Gültigkeitsbereich zu deklarieren, der eine Gruppe von verwandten Objekten enthält.</span><span class="sxs-lookup"><span data-stu-id="a9e19-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="a9e19-104">Sie können einen Namespace verwenden, um Codeelemente zu organisieren und global eindeutige Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9e19-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="a9e19-105">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="a9e19-105">Remarks</span></span>

<span data-ttu-id="a9e19-106">Innerhalb eines Namespace können Sie 0 (null) oder mehr der folgenden Typen deklarieren:</span><span class="sxs-lookup"><span data-stu-id="a9e19-106">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="a9e19-107">einen anderen Namespace</span><span class="sxs-lookup"><span data-stu-id="a9e19-107">another namespace</span></span>

- [<span data-ttu-id="a9e19-108">class</span><span class="sxs-lookup"><span data-stu-id="a9e19-108">class</span></span>](class.md)

- [<span data-ttu-id="a9e19-109">interface</span><span class="sxs-lookup"><span data-stu-id="a9e19-109">interface</span></span>](interface.md)

- [<span data-ttu-id="a9e19-110">struct</span><span class="sxs-lookup"><span data-stu-id="a9e19-110">struct</span></span>](struct.md)

- [<span data-ttu-id="a9e19-111">enum</span><span class="sxs-lookup"><span data-stu-id="a9e19-111">enum</span></span>](enum.md)

- [<span data-ttu-id="a9e19-112">delegate</span><span class="sxs-lookup"><span data-stu-id="a9e19-112">delegate</span></span>](delegate.md)

<span data-ttu-id="a9e19-113">Unabhängig davon, ob Sie einen Namespace in einer C#-Quelldatei explizit deklarieren, fügt der Compiler einen Standardnamespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="a9e19-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="a9e19-114">Dieser unbenannte Namespace, der manchmal auch als der globale Namespace bezeichnet wird, ist in jeder Datei vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a9e19-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="a9e19-115">Jeder Bezeichner im globalen Namespace ist für die Verwendung in einem benannten Namespace verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a9e19-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="a9e19-116">Namespaces verfügen implizit über öffentlichen Zugriff, und dies kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a9e19-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="a9e19-117">Eine Erläuterung der Zugriffsmodifizierer, die Sie einem Element in einem Namespace zuweisen können, finden Sie unter [Zugriffsmodifizierer](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="a9e19-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="a9e19-118">Es ist möglich, einen Namespace in zwei oder mehr Deklarationen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a9e19-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="a9e19-119">Im folgenden Beispiel werden beispielsweise zwei Klassen als Teil des `MyCompany`-Namespace definiert:</span><span class="sxs-lookup"><span data-stu-id="a9e19-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="a9e19-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9e19-120">Example</span></span>

<span data-ttu-id="a9e19-121">Im folgenden Beispiel wird veranschaulicht, wie eine statische Methode in einem geschachtelten Namespace aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a9e19-121">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="related-resources"></a><span data-ttu-id="a9e19-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9e19-122">Related resources</span></span>

<span data-ttu-id="a9e19-123">Weitere Informationen zur Verwendung von Namespaces finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="a9e19-123">For more information about using namespaces, see the following topics:</span></span>

- [<span data-ttu-id="a9e19-124">Namespaces</span><span class="sxs-lookup"><span data-stu-id="a9e19-124">Namespaces</span></span>](../../programming-guide/namespaces/index.md)

- [<span data-ttu-id="a9e19-125">Using-Namespaces</span><span class="sxs-lookup"><span data-stu-id="a9e19-125">Using Namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)

- [<span data-ttu-id="a9e19-126">Vorgehensweise: Verwenden des globalen Namespacealias</span><span class="sxs-lookup"><span data-stu-id="a9e19-126">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="a9e19-127">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="a9e19-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a9e19-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9e19-128">See also</span></span>

- [<span data-ttu-id="a9e19-129">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a9e19-129">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="a9e19-130">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a9e19-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a9e19-131">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a9e19-131">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a9e19-132">Namespaceschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a9e19-132">Namespace Keywords</span></span>](namespace-keywords.md)
- [<span data-ttu-id="a9e19-133">using</span><span class="sxs-lookup"><span data-stu-id="a9e19-133">using</span></span>](using-directive.md)
- [<span data-ttu-id="a9e19-134">using static</span><span class="sxs-lookup"><span data-stu-id="a9e19-134">using static</span></span>](using-static.md)