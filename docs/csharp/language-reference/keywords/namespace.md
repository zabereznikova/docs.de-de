---
description: namespace-Schlüsselwort – C#-Programmierreferenz
title: namespace-Schlüsselwort – C#-Programmierreferenz
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: a6cfd1c3d37cbdef1f0dd72ddca85ce91f2e183b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139579"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="fe6d3-103">Namespace (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="fe6d3-103">namespace (C# Reference)</span></span>

<span data-ttu-id="fe6d3-104">Das `namespace`-Schlüsselwort wird verwendet, um einen Gültigkeitsbereich zu deklarieren, der eine Gruppe von verwandten Objekten enthält.</span><span class="sxs-lookup"><span data-stu-id="fe6d3-104">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="fe6d3-105">Sie können einen Namespace verwenden, um Codeelemente zu organisieren und global eindeutige Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fe6d3-105">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="fe6d3-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fe6d3-106">Remarks</span></span>

<span data-ttu-id="fe6d3-107">Innerhalb eines Namespace können Sie 0 (null) oder mehr der folgenden Typen deklarieren:</span><span class="sxs-lookup"><span data-stu-id="fe6d3-107">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="fe6d3-108">einen anderen Namespace</span><span class="sxs-lookup"><span data-stu-id="fe6d3-108">another namespace</span></span>

- [<span data-ttu-id="fe6d3-109">class</span><span class="sxs-lookup"><span data-stu-id="fe6d3-109">class</span></span>](class.md)

- [<span data-ttu-id="fe6d3-110">interface</span><span class="sxs-lookup"><span data-stu-id="fe6d3-110">interface</span></span>](interface.md)

- [<span data-ttu-id="fe6d3-111">struct</span><span class="sxs-lookup"><span data-stu-id="fe6d3-111">struct</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="fe6d3-112">enum</span><span class="sxs-lookup"><span data-stu-id="fe6d3-112">enum</span></span>](../builtin-types/enum.md)

- [<span data-ttu-id="fe6d3-113">delegate</span><span class="sxs-lookup"><span data-stu-id="fe6d3-113">delegate</span></span>](../builtin-types/reference-types.md#the-delegate-type)

<span data-ttu-id="fe6d3-114">Unabhängig davon, ob Sie einen Namespace in einer C#-Quelldatei explizit deklarieren, fügt der Compiler einen Standardnamespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="fe6d3-114">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="fe6d3-115">Dieser unbenannte Namespace, der manchmal auch als der globale Namespace bezeichnet wird, ist in jeder Datei vorhanden.</span><span class="sxs-lookup"><span data-stu-id="fe6d3-115">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="fe6d3-116">Jeder Bezeichner im globalen Namespace ist für die Verwendung in einem benannten Namespace verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fe6d3-116">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="fe6d3-117">Namespaces verfügen implizit über öffentlichen Zugriff, und dies kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fe6d3-117">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="fe6d3-118">Eine Erläuterung der Zugriffsmodifizierer, die Sie einem Element in einem Namespace zuweisen können, finden Sie unter [Zugriffsmodifizierer](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="fe6d3-118">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="fe6d3-119">Es ist möglich, einen Namespace in zwei oder mehr Deklarationen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="fe6d3-119">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="fe6d3-120">Im folgenden Beispiel werden beispielsweise zwei Klassen als Teil des `MyCompany`-Namespace definiert:</span><span class="sxs-lookup"><span data-stu-id="fe6d3-120">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="fe6d3-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe6d3-121">Example</span></span>

<span data-ttu-id="fe6d3-122">Im folgenden Beispiel wird veranschaulicht, wie eine statische Methode in einem geschachtelten Namespace aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fe6d3-122">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="fe6d3-123">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="fe6d3-123">C# language specification</span></span>

<span data-ttu-id="fe6d3-124">Weitere Informationen finden Sie im Abschnitt [Namespaces](~/_csharplang/spec/namespaces.md) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="fe6d3-124">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fe6d3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe6d3-125">See also</span></span>

- [<span data-ttu-id="fe6d3-126">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="fe6d3-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="fe6d3-127">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="fe6d3-127">C# keywords</span></span>](index.md)
- [<span data-ttu-id="fe6d3-128">using</span><span class="sxs-lookup"><span data-stu-id="fe6d3-128">using</span></span>](using-directive.md)
- [<span data-ttu-id="fe6d3-129">using static</span><span class="sxs-lookup"><span data-stu-id="fe6d3-129">using static</span></span>](using-static.md)
- [<span data-ttu-id="fe6d3-130">Namespacealias-Qualifizierer `::`</span><span class="sxs-lookup"><span data-stu-id="fe6d3-130">Namespace alias qualifier `::`</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="fe6d3-131">Namespaces</span><span class="sxs-lookup"><span data-stu-id="fe6d3-131">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
