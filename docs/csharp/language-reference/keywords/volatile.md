---
title: volatile (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: be7e081b18702710c00b5b86a9bc152800f0cf3d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526218"
---
# <a name="volatile-c-reference"></a><span data-ttu-id="ec5e5-102">volatile (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ec5e5-102">volatile (C# Reference)</span></span>
<span data-ttu-id="ec5e5-103">Das Schlüsselwort `volatile` gibt an, dass ein Feld von mehreren Threads geändert werden kann, die zur gleichen Zeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="ec5e5-104">Felder, die als `volatile` deklariert sind, unterliegen keinen Compileroptimierungen, die von Zugriff durch einen einzelnen Thread ausgehen.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="ec5e5-105">Diese Einschränkungen stellen sicher, dass alle Threads volatile-Schreibvorgänge, die von einem anderen Thread ausgeführt werden, in der Reihenfolge ihrer Ausführung berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-105">These restrictions ensure that all threads will observe volatile writes performed by any other thread in the order in which they were performed.</span></span> <span data-ttu-id="ec5e5-106">Es gibt keine Garantie für eine einzelne Gesamtsortierung von volatile-Schreibvorgängen aus der Sicht aller ausgeführten Threads.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-106">There is no guarantee of a single total ordering of volatile writes as seen from all threads of execution.</span></span>  
  
 <span data-ttu-id="ec5e5-107">Der `volatile`-Modifizierer wird normalerweise für Felder verwendet, auf die von mehreren Threads ohne die [lock](../../../csharp/language-reference/keywords/lock-statement.md)-Anweisung zugegriffen wird, um den Zugriff zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-107">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="ec5e5-108">Das Schlüsselwort `volatile` kann auf Felder der folgenden Typen angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="ec5e5-108">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="ec5e5-109">Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-109">Reference types.</span></span>  
  
-   <span data-ttu-id="ec5e5-110">Zeigertypen (in unsicherem Kontext).</span><span class="sxs-lookup"><span data-stu-id="ec5e5-110">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="ec5e5-111">Beachten Sie, dass der Zeiger selbst als „volatile“ deklariert sein kann, das Objekt, auf das er zeigt aber nicht.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-111">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="ec5e5-112">Anders ausgedrückt können Sie keinen „Zeiger auf ‚volatile‘“ deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-112">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="ec5e5-113">Typen wie sbyte, byte, short, ushort, int, uint, char, float und bool.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-113">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="ec5e5-114">Ein Enumerationstyp mit einem der folgenden Basistypen: byte, sbyte, short, ushort, int oder uint.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-114">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="ec5e5-115">Generische Typparameter, die als Verweistypen bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-115">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="ec5e5-116"><xref:System.IntPtr> und <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-116"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="ec5e5-117">Das Schlüsselwort „volatile“ kann nur auf Felder einer Klasse oder Struktur angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-117">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="ec5e5-118">Lokale Variablen können nicht als `volatile` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-118">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec5e5-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec5e5-119">Example</span></span>  
 <span data-ttu-id="ec5e5-120">Im folgenden Beispiel wird die Deklaration einer öffentlichen Feldvariable als `volatile` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-120">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="ec5e5-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec5e5-121">Example</span></span>  
 <span data-ttu-id="ec5e5-122">Im folgenden Beispiel wird veranschaulicht, wie ein Hilfs- oder Arbeitsthread erstellt wird und für das Ausführen der Verarbeitung parallel mit dem primären Thread verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ec5e5-122">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="ec5e5-123">Hintergrundinformationen zum Multithreading finden Sie unter [Verwaltetes Threading](../../../standard/threading/index.md) und [Threading (C#)](../../programming-guide/concepts/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="ec5e5-123">For background information about multithreading, see [Managed Threading](../../../standard/threading/index.md) and [Threading (C#)](../../programming-guide/concepts/threading/index.md).</span></span>  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ec5e5-124">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="ec5e5-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ec5e5-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec5e5-125">See Also</span></span>

- [<span data-ttu-id="ec5e5-126">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ec5e5-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ec5e5-127">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ec5e5-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ec5e5-128">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ec5e5-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="ec5e5-129">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="ec5e5-129">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
