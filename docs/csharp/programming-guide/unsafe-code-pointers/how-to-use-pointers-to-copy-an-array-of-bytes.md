---
title: 'Gewusst wie: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierhandbuch)'
ms.date: 04/20/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6e87a2ec2c04812ac9b998c4c6d9a18d1b097342
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a><span data-ttu-id="b55dd-102">Gewusst wie: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b55dd-102">How to: Use Pointers to Copy an Array of Bytes  (C# Programming Guide)</span></span>

<span data-ttu-id="b55dd-103">In folgendem Beispiel werden Zeiger verwendet, um Bytes aus einem Array in ein anderes zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="b55dd-103">The following example uses pointers to copy bytes from one array to another.</span></span>

<span data-ttu-id="b55dd-104">In diesem Beispiel wird das Schlüsselwort [unsafe](../../language-reference/keywords/unsafe.md) verwendet, mit dem Sie Zeiger in der `Copy`-Methode verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b55dd-104">This example uses the [unsafe](../../language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="b55dd-105">Die Anweisung [fixed](../../language-reference/keywords/fixed-statement.md) wird verwendet, um Zeiger auf das Quell- und Zielarray zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b55dd-105">The [fixed](../../language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="b55dd-106">Diese `fixed`-Anweisung *heftet* den Speicherort des Quell- und Zielarrays im Speicher an, damit diese während der automatischen Speicherbereinigung nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="b55dd-106">The `fixed` statement *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="b55dd-107">Die Speicherblöcke der Arrays werden gelöst, wenn der `fixed`-Block abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="b55dd-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="b55dd-108">Da die `Copy`-Methode in diesem Beispiel das Schlüsselwort `unsafe` verwendet, muss sie mit der Compileroption [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="b55dd-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>

<span data-ttu-id="b55dd-109">In diesem Beispiel werden Indizes anstelle eines zweiten nicht verwalteten Zeigers verwendet, um auf die Elemente beider Arrays zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="b55dd-109">This example accesses the elements of both arrays using indices rather than a second unmanaged pointer.</span></span> <span data-ttu-id="b55dd-110">Die Deklaration der Zeiger `pSource` und `pTarget` heftet die Arrays an.</span><span class="sxs-lookup"><span data-stu-id="b55dd-110">The declaration of the `pSource` and `pTarget` pointers pins the arrays.</span></span> <span data-ttu-id="b55dd-111">Dieses Feature ist ab C# 7.3 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b55dd-111">This feature is available starting with C# 7.3.</span></span>

## <a name="example"></a><span data-ttu-id="b55dd-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b55dd-112">Example</span></span>

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a><span data-ttu-id="b55dd-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b55dd-113">See Also</span></span>
 [<span data-ttu-id="b55dd-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b55dd-114">C# Programming Guide</span></span>](../index.md)  
 [<span data-ttu-id="b55dd-115">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="b55dd-115">Unsafe Code and Pointers</span></span>](index.md)  
 [<span data-ttu-id="b55dd-116">-unsafe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="b55dd-116">-unsafe (C# Compiler Options)</span></span>](../../language-reference/compiler-options/unsafe-compiler-option.md)  
 [<span data-ttu-id="b55dd-117">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="b55dd-117">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)  
