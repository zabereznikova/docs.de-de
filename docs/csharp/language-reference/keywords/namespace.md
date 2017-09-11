---
title: Namespace (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- namespace_CSharpKeyword
- namespace
dev_langs:
- CSharp
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d2cef3949d9a41db36406db059218f7a204172ea
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="namespace-c-reference"></a><span data-ttu-id="1a402-102">Namespace (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1a402-102">namespace (C# Reference)</span></span>
<span data-ttu-id="1a402-103">Das `namespace`-Schlüsselwort wird verwendet, um einen Gültigkeitsbereich zu deklarieren, der eine Gruppe von verwandten Objekten enthält.</span><span class="sxs-lookup"><span data-stu-id="1a402-103">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="1a402-104">Sie können einen Namespace verwenden, um Codeelemente zu organisieren und global eindeutige Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1a402-104">You can use a namespace to organize code elements and to create globally unique types.</span></span>  
  
 <span data-ttu-id="1a402-105">[!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a402-105">[!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a402-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1a402-106">Remarks</span></span>  
 <span data-ttu-id="1a402-107">Innerhalb eines Namespace können Sie einen oder mehrere der folgenden Typen deklarieren:</span><span class="sxs-lookup"><span data-stu-id="1a402-107">Within a namespace, you can declare one or more of the following types:</span></span>  
  
-   <span data-ttu-id="1a402-108">einen anderen Namespace</span><span class="sxs-lookup"><span data-stu-id="1a402-108">another namespace</span></span>  
  
-   [<span data-ttu-id="1a402-109">class</span><span class="sxs-lookup"><span data-stu-id="1a402-109">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
  
-   [<span data-ttu-id="1a402-110">interface</span><span class="sxs-lookup"><span data-stu-id="1a402-110">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
  
-   [<span data-ttu-id="1a402-111">struct</span><span class="sxs-lookup"><span data-stu-id="1a402-111">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="1a402-112">enum</span><span class="sxs-lookup"><span data-stu-id="1a402-112">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
-   [<span data-ttu-id="1a402-113">delegate</span><span class="sxs-lookup"><span data-stu-id="1a402-113">delegate</span></span>](../../../csharp/language-reference/keywords/delegate.md)  
  
 <span data-ttu-id="1a402-114">Unabhängig davon, ob Sie einen Namespace in einer C#-Quelldatei explizit deklarieren, fügt der Compiler einen Standardnamespace hinzu.</span><span class="sxs-lookup"><span data-stu-id="1a402-114">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="1a402-115">Dieser unbenannte Namespace, der manchmal auch als der globale Namespace bezeichnet wird, ist in jeder Datei vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1a402-115">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="1a402-116">Jeder Bezeichner im globalen Namespace ist für die Verwendung in einem benannten Namespace verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1a402-116">Any identifier in the global namespace is available for use in a named namespace.</span></span>  
  
 <span data-ttu-id="1a402-117">Namespaces verfügen implizit über öffentlichen Zugriff, und dies kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1a402-117">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="1a402-118">Eine Erläuterung der Zugriffsmodifizierer, die Sie einem Element in einem Namespace zuweisen können, finden Sie unter [Zugriffsmodifizierer](../../../csharp/language-reference/keywords/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="1a402-118">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="1a402-119">Es ist möglich, einen Namespace in zwei oder mehr Deklarationen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1a402-119">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="1a402-120">Im folgenden Beispiel werden beispielsweise zwei Klassen als Teil des `MyCompany`-Namespace definiert:</span><span class="sxs-lookup"><span data-stu-id="1a402-120">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>  
  
 <span data-ttu-id="1a402-121">[!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a402-121">[!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a402-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a402-122">Example</span></span>  
 <span data-ttu-id="1a402-123">Im folgenden Beispiel wird veranschaulicht, wie eine statische Methode in einem geschachtelten Namespace aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="1a402-123">The following example shows how to call a static method in a nested namespace.</span></span>  
  
 <span data-ttu-id="1a402-124">[!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="1a402-124">[!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="1a402-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a402-125">For More Information</span></span>  
 <span data-ttu-id="1a402-126">Weitere Informationen zur Verwendung von Namespaces finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1a402-126">For more information about using namespaces, see the following topics:</span></span>  
  
-   [<span data-ttu-id="1a402-127">Namespaces</span><span class="sxs-lookup"><span data-stu-id="1a402-127">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [<span data-ttu-id="1a402-128">Using-Namespaces</span><span class="sxs-lookup"><span data-stu-id="1a402-128">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [<span data-ttu-id="1a402-129">Gewusst wie: Verwenden des globalen Namespacealias</span><span class="sxs-lookup"><span data-stu-id="1a402-129">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="1a402-130">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="1a402-130">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1a402-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a402-131">See Also</span></span>  
 <span data-ttu-id="1a402-132">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a402-132">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1a402-133">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a402-133">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1a402-134">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="1a402-134">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="1a402-135">[Namespaceschlüsselwörter](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="1a402-135">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 [<span data-ttu-id="1a402-136">using</span><span class="sxs-lookup"><span data-stu-id="1a402-136">using</span></span>](../../../csharp/language-reference/keywords/using.md)

