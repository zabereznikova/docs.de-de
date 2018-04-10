---
title: volatile (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1cefa39313c3c551e8d05fbc31e528b86c6888d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="volatile-c-reference"></a><span data-ttu-id="08c53-102">volatile (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="08c53-102">volatile (C# Reference)</span></span>
<span data-ttu-id="08c53-103">Das Schlüsselwort `volatile` gibt an, dass ein Feld von mehreren Threads geändert werden kann, die zur gleichen Zeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="08c53-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="08c53-104">Felder, die als `volatile` deklariert sind, unterliegen keinen Compileroptimierungen, die von Zugriff durch einen einzelnen Thread ausgehen.</span><span class="sxs-lookup"><span data-stu-id="08c53-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="08c53-105">Dadurch wird sichergestellt, dass immer der aktuelle Wert im Feld vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="08c53-105">This ensures that the most up-to-date value is present in the field at all times.</span></span>  
  
 <span data-ttu-id="08c53-106">Der `volatile`-Modifizierer wird normalerweise für Felder verwendet, auf die von mehreren Threads ohne die [lock](../../../csharp/language-reference/keywords/lock-statement.md)-Anweisung zugegriffen wird, um den Zugriff zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="08c53-106">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="08c53-107">Das Schlüsselwort `volatile` kann auf Felder der folgenden Typen angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="08c53-107">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="08c53-108">Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="08c53-108">Reference types.</span></span>  
  
-   <span data-ttu-id="08c53-109">Zeigertypen (in unsicherem Kontext).</span><span class="sxs-lookup"><span data-stu-id="08c53-109">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="08c53-110">Beachten Sie, dass der Zeiger selbst als „volatile“ deklariert sein kann, das Objekt, auf das er zeigt aber nicht.</span><span class="sxs-lookup"><span data-stu-id="08c53-110">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="08c53-111">Anders ausgedrückt können Sie keinen „Zeiger auf ‚volatile‘“ deklarieren.</span><span class="sxs-lookup"><span data-stu-id="08c53-111">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="08c53-112">Typen wie sbyte, byte, short, ushort, int, uint, char, float und bool.</span><span class="sxs-lookup"><span data-stu-id="08c53-112">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="08c53-113">Ein Enumerationstyp mit einem der folgenden Basistypen: byte, sbyte, short, ushort, int oder uint.</span><span class="sxs-lookup"><span data-stu-id="08c53-113">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="08c53-114">Generische Typparameter, die als Verweistypen bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="08c53-114">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="08c53-115"><xref:System.IntPtr> und <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="08c53-115"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="08c53-116">Das Schlüsselwort „volatile“ kann nur auf Felder einer Klasse oder Struktur angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="08c53-116">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="08c53-117">Lokale Variablen können nicht als `volatile` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="08c53-117">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08c53-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08c53-118">Example</span></span>  
 <span data-ttu-id="08c53-119">Im folgenden Beispiel wird die Deklaration einer öffentlichen Feldvariable als `volatile` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="08c53-119">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="08c53-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="08c53-120">Example</span></span>  
 <span data-ttu-id="08c53-121">Im folgenden Beispiel wird veranschaulicht, wie ein Hilfs- oder Arbeitsthread erstellt wird und für das Ausführen der Verarbeitung parallel mit dem primären Thread verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="08c53-121">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="08c53-122">Hintergrundinformationen zum Multithreading finden Sie unter [Threading](../../../standard/threading/index.md) und [Threading](../../programming-guide/concepts/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="08c53-122">For background information about multithreading, see [Threading](../../../standard/threading/index.md) and [Threading](../../programming-guide/concepts/threading/index.md).</span></span>  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="08c53-123">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="08c53-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="08c53-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08c53-124">See Also</span></span>  
 [<span data-ttu-id="08c53-125">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="08c53-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="08c53-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="08c53-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="08c53-127">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="08c53-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="08c53-128">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="08c53-128">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
