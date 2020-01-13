---
title: volatile – C#-Referenz
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: c7a6c442c33ac2b41f652805837f455a957819de
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712844"
---
# <a name="volatile-c-reference"></a><span data-ttu-id="61ec1-102">volatile (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="61ec1-102">volatile (C# Reference)</span></span>

<span data-ttu-id="61ec1-103">Das Schlüsselwort `volatile` gibt an, dass ein Feld von mehreren Threads geändert werden kann, die zur gleichen Zeit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="61ec1-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="61ec1-104">Der Compiler, das Runtimesystem und sogar die Hardware können aus Leistungsgründen die Lese- und Schreibvorgänge in den Speicherorten neu anordnen.</span><span class="sxs-lookup"><span data-stu-id="61ec1-104">The compiler, the runtime system, and even hardware may rearrange reads and writes to memory locations for performance reasons.</span></span> <span data-ttu-id="61ec1-105">Felder, die als `volatile` deklariert sind, sind von dieser Optimierungen nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="61ec1-105">Fields that are declared `volatile` are not subject to these optimizations.</span></span> <span data-ttu-id="61ec1-106">Durch Hinzufügen des `volatile`-Modifizierers stellen Sie sicher, dass alle Threads volatile Schreibvorgänge, die von einem anderen Thread ausgeführt werden, in der Reihenfolge ihrer Ausführung berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="61ec1-106">Adding the `volatile` modifier ensures that all threads will observe volatile writes performed by any other thread in the order in which they were performed.</span></span> <span data-ttu-id="61ec1-107">Es gibt keine Garantie für eine einzelne Gesamtsortierung von volatile-Schreibvorgängen aus der Sicht aller ausgeführten Threads.</span><span class="sxs-lookup"><span data-stu-id="61ec1-107">There is no guarantee of a single total ordering of volatile writes as seen from all threads of execution.</span></span>

<span data-ttu-id="61ec1-108">Das Schlüsselwort `volatile` kann auf Felder der folgenden Typen angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="61ec1-108">The `volatile` keyword can be applied to fields of these types:</span></span>

- <span data-ttu-id="61ec1-109">Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="61ec1-109">Reference types.</span></span>
- <span data-ttu-id="61ec1-110">Zeigertypen (in unsicherem Kontext).</span><span class="sxs-lookup"><span data-stu-id="61ec1-110">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="61ec1-111">Beachten Sie, dass der Zeiger selbst als „volatile“ deklariert sein kann, das Objekt, auf das er zeigt aber nicht.</span><span class="sxs-lookup"><span data-stu-id="61ec1-111">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="61ec1-112">Anders ausgedrückt können Sie keinen „Zeiger auf ‚volatile‘“ deklarieren.</span><span class="sxs-lookup"><span data-stu-id="61ec1-112">In other words, you cannot declare a "pointer to volatile."</span></span>
- <span data-ttu-id="61ec1-113">Einfacher Typen wie `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float` und `bool`.</span><span class="sxs-lookup"><span data-stu-id="61ec1-113">Simple types such as `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float`, and `bool`.</span></span>
- <span data-ttu-id="61ec1-114">Ein `enum`-Typ mit einem der folgenden Basistypen: `byte`, `sbyte`, `short`, `ushort`, `int` oder `uint`.</span><span class="sxs-lookup"><span data-stu-id="61ec1-114">An `enum` type with one of the following base types: `byte`, `sbyte`, `short`, `ushort`, `int`, or `uint`.</span></span>
- <span data-ttu-id="61ec1-115">Generische Typparameter, die als Verweistypen bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="61ec1-115">Generic type parameters known to be reference types.</span></span>
- <span data-ttu-id="61ec1-116"><xref:System.IntPtr> und <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="61ec1-116"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>

<span data-ttu-id="61ec1-117">Andere Typen, einschließlich `double` und `long`, können nicht mit `volatile` markiert werden, da Lese- und Schreibvorgänge in die Felder dieser Typen nicht unbedingt atomar sind.</span><span class="sxs-lookup"><span data-stu-id="61ec1-117">Other types, including `double` and `long`, cannot be marked `volatile` because reads and writes to fields of those types cannot be guaranteed to be atomic.</span></span> <span data-ttu-id="61ec1-118">Um den Multithreadzugriff auf diese Feldtypen zu schützen, verwenden Sie die Klassenmitglieder <xref:System.Threading.Interlocked> oder schützen Sie den Zugriff mit der Anweisung [`lock`](lock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="61ec1-118">To protect multi-threaded access to those types of fields, use the <xref:System.Threading.Interlocked> class members or protect access using the [`lock`](lock-statement.md) statement.</span></span>

<span data-ttu-id="61ec1-119">Das Schlüsselwort `volatile` kann nur auf Felder einer `class` oder `struct` angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="61ec1-119">The `volatile` keyword can only be applied to fields of a `class` or `struct`.</span></span> <span data-ttu-id="61ec1-120">Lokale Variablen können nicht als `volatile` deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="61ec1-120">Local variables cannot be declared `volatile`.</span></span>

## <a name="example"></a><span data-ttu-id="61ec1-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61ec1-121">Example</span></span>

<span data-ttu-id="61ec1-122">Im folgenden Beispiel wird die Deklaration einer öffentlichen Feldvariable als `volatile` dargestellt.</span><span class="sxs-lookup"><span data-stu-id="61ec1-122">The following example shows how to declare a public field variable as `volatile`.</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

<span data-ttu-id="61ec1-123">Im folgenden Beispiel wird veranschaulicht, wie ein Hilfs- oder Arbeitsthread erstellt wird und für das Ausführen der Verarbeitung parallel mit dem primären Thread verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="61ec1-123">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="61ec1-124">Weitere Informationen zum Multithreading finden Sie unter [Verwaltetes Threading](../../../standard/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="61ec1-124">For more information about multithreading, see [Managed Threading](../../../standard/threading/index.md).</span></span>

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

<span data-ttu-id="61ec1-125">Wenn der `volatile`-Modifizierer der Deklaration von `_shouldStop` hinzugefügt wird, erhalten Sie immer die gleichen Ergebnisse (ähnlich dem Auszug aus dem vorhergehenden Code).</span><span class="sxs-lookup"><span data-stu-id="61ec1-125">With the `volatile` modifier added to the declaration of `_shouldStop` in place, you'll always get the same results (similar to the excerpt shown in the preceding code).</span></span> <span data-ttu-id="61ec1-126">Ohne diesen Modifizierer für das `_shouldStop`-Mitglied ist das Verhalten unvorhersehbar.</span><span class="sxs-lookup"><span data-stu-id="61ec1-126">However, without that modifier on the `_shouldStop` member, the behavior is unpredictable.</span></span> <span data-ttu-id="61ec1-127">Die `DoWork`-Methode kann den Mitgliederzugriff optimieren, was zum Lesen veralteter Daten führt.</span><span class="sxs-lookup"><span data-stu-id="61ec1-127">The `DoWork` method may optimize the member access, resulting in reading stale data.</span></span> <span data-ttu-id="61ec1-128">Aufgrund der Natur der Multithreadprogrammierung ist die Anzahl der veraltete Lesevorgänge unvorhersehbar.</span><span class="sxs-lookup"><span data-stu-id="61ec1-128">Because of the nature of multi-threaded programming, the number of stale reads is unpredictable.</span></span> <span data-ttu-id="61ec1-129">Verschiedene Programmläufe führen zu etwas unterschiedlichen Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="61ec1-129">Different runs of the program will produce somewhat different results.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="61ec1-130">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="61ec1-130">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="61ec1-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61ec1-131">See also</span></span>

- [<span data-ttu-id="61ec1-132">C#-Sprachspezifikation: Schlüsselwort „volatile“</span><span class="sxs-lookup"><span data-stu-id="61ec1-132">C# language specification: volatile keyword</span></span>](../../../../_csharplang/spec/classes.md#volatile-fields)
- [<span data-ttu-id="61ec1-133">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="61ec1-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="61ec1-134">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="61ec1-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="61ec1-135">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="61ec1-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="61ec1-136">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="61ec1-136">Modifiers</span></span>](index.md)
- [<span data-ttu-id="61ec1-137">lock-Anweisung</span><span class="sxs-lookup"><span data-stu-id="61ec1-137">lock statement</span></span>](lock-statement.md)
- <xref:System.Threading.Interlocked>
