---
title: Namespace (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: "28"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 76cc1adc21f6cfadc93da58250336705e43e333a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-c-reference"></a><span data-ttu-id="c04aa-102">Namespace (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c04aa-102">namespace (C# Reference)</span></span>
<span data-ttu-id="c04aa-103">Das `namespace`-Schlüsselwort wird verwendet, um einen Gültigkeitsbereich zu deklarieren, der eine Gruppe von verwandten Objekten enthält.</span><span class="sxs-lookup"><span data-stu-id="c04aa-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="c04aa-104">Sie können einen Namespace verwenden, um Codeelemente zu organisieren und global eindeutige Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c04aa-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="c04aa-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c04aa-105">Remarks</span></span>  
 <span data-ttu-id="c04aa-106">Innerhalb eines Namespace können Sie einen oder mehrere der folgenden Typen deklarieren:</span><span class="sxs-lookup"><span data-stu-id="c04aa-106">Within a namespace, you can declare one or more of the following types:</span></span>  
  
-   <span data-ttu-id="c04aa-107">einen anderen Namespace</span><span class="sxs-lookup"><span data-stu-id="c04aa-107">another namespace</span></span>  
  
-   [<span data-ttu-id="c04aa-108">class</span><span class="sxs-lookup"><span data-stu-id="c04aa-108">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="c04aa-109">interface</span><span class="sxs-lookup"><span data-stu-id="c04aa-109">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="c04aa-110">struct</span><span class="sxs-lookup"><span data-stu-id="c04aa-110">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="c04aa-111">enum</span><span class="sxs-lookup"><span data-stu-id="c04aa-111">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
-   [<span data-ttu-id="c04aa-112">delegate</span><span class="sxs-lookup"><span data-stu-id="c04aa-112">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="c04aa-113">Unabhängig davon, ob Sie einen Namespace in einer C#-Quelldatei explizit deklarieren, fügt der Compiler einen Standardnamespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="c04aa-113">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="c04aa-114">Dieser unbenannte Namespace, der manchmal auch als der globale Namespace bezeichnet wird, ist in jeder Datei vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c04aa-114">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="c04aa-115">Jeder Bezeichner im globalen Namespace ist für die Verwendung in einem benannten Namespace verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c04aa-115">Any identifier in the global namespace is available for use in a named namespace.</span></span>  
  
 <span data-ttu-id="c04aa-116">Namespaces verfügen implizit über öffentlichen Zugriff, und dies kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c04aa-116">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="c04aa-117">Eine Erläuterung der Zugriffsmodifizierer, die Sie einem Element in einem Namespace zuweisen können, finden Sie unter [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="c04aa-117">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="c04aa-118">Es ist möglich, einen Namespace in zwei oder mehr Deklarationen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="c04aa-118">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="c04aa-119">Im folgenden Beispiel werden beispielsweise zwei Klassen als Teil des `MyCompany`-Namespace definiert:</span><span class="sxs-lookup"><span data-stu-id="c04aa-119">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="c04aa-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c04aa-120">Example</span></span>  
 <span data-ttu-id="c04aa-121">Im folgenden Beispiel wird veranschaulicht, wie eine statische Methode in einem geschachtelten Namespace aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c04aa-121">The following example shows how to call a static method in a nested namespace.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]  
  
## <a name="for-more-information"></a><span data-ttu-id="c04aa-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c04aa-122">For More Information</span></span>  
 <span data-ttu-id="c04aa-123">Weitere Informationen zur Verwendung von Namespaces finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c04aa-123">For more information about using namespaces, see the following topics:</span></span>  
  
-   [<span data-ttu-id="c04aa-124">Namespaces</span><span class="sxs-lookup"><span data-stu-id="c04aa-124">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="c04aa-125">Using-Namespaces</span><span class="sxs-lookup"><span data-stu-id="c04aa-125">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="c04aa-126">Gewusst wie: Verwenden des globalen Namespacealias</span><span class="sxs-lookup"><span data-stu-id="c04aa-126">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="c04aa-127">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="c04aa-127">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c04aa-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c04aa-128">See Also</span></span>  
 [<span data-ttu-id="c04aa-129">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c04aa-129">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c04aa-130">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c04aa-130">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c04aa-131">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c04aa-131">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="c04aa-132">Namespaceschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c04aa-132">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="c04aa-133">using</span><span class="sxs-lookup"><span data-stu-id="c04aa-133">using</span></span>](../../../csharp/language-reference/keywords/using.md)
