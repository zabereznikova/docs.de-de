---
title: volatile (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- volatile_CSharpKeyword
- volatile
dev_langs:
- CSharp
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 29
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
ms.openlocfilehash: c8f9fba15991197be885a973435089098a57db87
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="volatile-c-reference"></a><span data-ttu-id="9eb68-102">volatile (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9eb68-102">volatile (C# Reference)</span></span>
<span data-ttu-id="9eb68-103">Das Schlüsselwort `volatile` gibt an, dass ein Feld von mehreren Threads geändert werden kann, die zur gleichen Zeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9eb68-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="9eb68-104">Felder, die als `volatile` deklariert sind, unterliegen keinen Compileroptimierungen, die von Zugriff durch einen einzelnen Thread ausgehen.</span><span class="sxs-lookup"><span data-stu-id="9eb68-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="9eb68-105">Dadurch wird sichergestellt, dass immer der aktuelle Wert im Feld vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9eb68-105">This ensures that the most up-to-date value is present in the field at all times.</span></span>  
  
 <span data-ttu-id="9eb68-106">Der `volatile`-Modifizierer wird normalerweise für Felder verwendet, auf die von mehreren Threads ohne die [lock](../../../csharp/language-reference/keywords/lock-statement.md)-Anweisung zugegriffen wird, um den Zugriff zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="9eb68-106">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="9eb68-107">Das Schlüsselwort `volatile` kann auf Felder der folgenden Typen angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="9eb68-107">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="9eb68-108">Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="9eb68-108">Reference types.</span></span>  
  
-   <span data-ttu-id="9eb68-109">Zeigertypen (in unsicherem Kontext).</span><span class="sxs-lookup"><span data-stu-id="9eb68-109">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="9eb68-110">Beachten Sie, dass der Zeiger selbst als „volatile“ deklariert sein kann, das Objekt, auf das er zeigt aber nicht.</span><span class="sxs-lookup"><span data-stu-id="9eb68-110">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="9eb68-111">Anders ausgedrückt können Sie keinen „Zeiger auf ‚volatile‘“ deklarieren.</span><span class="sxs-lookup"><span data-stu-id="9eb68-111">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="9eb68-112">Typen wie sbyte, byte, short, ushort, int, uint, char, float und bool.</span><span class="sxs-lookup"><span data-stu-id="9eb68-112">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="9eb68-113">Ein Enumerationstyp mit einem der folgenden Basistypen: byte, sbyte, short, ushort, int oder uint.</span><span class="sxs-lookup"><span data-stu-id="9eb68-113">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="9eb68-114">Generische Typparameter, die als Verweistypen bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="9eb68-114">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="9eb68-115"><xref:System.IntPtr> und <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="9eb68-115"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="9eb68-116">Das Schlüsselwort „volatile“ kann nur auf Felder einer Klasse oder Struktur angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9eb68-116">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="9eb68-117">Lokale Variablen können nicht als `volatile` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="9eb68-117">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9eb68-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9eb68-118">Example</span></span>  
 <span data-ttu-id="9eb68-119">Im folgenden Beispiel wird die Deklaration einer öffentlichen Feldvariable als `volatile` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9eb68-119">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 <span data-ttu-id="9eb68-120">[!code-cs[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9eb68-120">[!code-cs[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="9eb68-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9eb68-121">Example</span></span>  
 <span data-ttu-id="9eb68-122">Im folgenden Beispiel wird veranschaulicht, wie ein Hilfs- oder Arbeitsthread erstellt wird und für das Ausführen der Verarbeitung parallel mit dem primären Thread verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9eb68-122">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="9eb68-123">Hintergrundinformationen zum Multithreading finden Sie unter [Threading](../../../standard/threading/index.md) und [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span><span class="sxs-lookup"><span data-stu-id="9eb68-123">For background information about multithreading, see [Threading](../../../standard/threading/index.md) and [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
 <span data-ttu-id="9eb68-124">[!code-cs[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9eb68-124">[!code-cs[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="9eb68-125">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="9eb68-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9eb68-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9eb68-126">See Also</span></span>  
 <span data-ttu-id="9eb68-127">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="9eb68-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="9eb68-128">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9eb68-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9eb68-129">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="9eb68-129">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="9eb68-130">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="9eb68-130">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

