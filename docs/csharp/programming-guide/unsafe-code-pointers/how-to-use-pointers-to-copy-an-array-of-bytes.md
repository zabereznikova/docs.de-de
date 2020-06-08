---
title: 'Vorgehensweise: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierleitfaden)'
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: 8c1afc06fb567a923d604ad53dc26f94178a8d60
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397414"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes-c-programming-guide"></a><span data-ttu-id="ad073-102">Vorgehensweise: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="ad073-102">How to use pointers to copy an array of bytes (C# Programming Guide)</span></span>

<span data-ttu-id="ad073-103">In folgendem Beispiel werden Zeiger verwendet, um Bytes aus einem Array in ein anderes zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="ad073-103">The following example uses pointers to copy bytes from one array to another.</span></span>

<span data-ttu-id="ad073-104">In diesem Beispiel wird das Schlüsselwort [unsafe](../../language-reference/keywords/unsafe.md) verwendet, mit dem Sie Zeiger in der `Copy`-Methode verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ad073-104">This example uses the [unsafe](../../language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="ad073-105">Die Anweisung [fixed](../../language-reference/keywords/fixed-statement.md) wird verwendet, um Zeiger auf das Quell- und Zielarray zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ad073-105">The [fixed](../../language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="ad073-106">Diese `fixed`-Anweisung *heftet* den Speicherort des Quell- und Zielarrays im Speicher an, damit diese während der automatischen Speicherbereinigung nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="ad073-106">The `fixed` statement *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="ad073-107">Die Speicherblöcke der Arrays werden gelöst, wenn der `fixed`-Block abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="ad073-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="ad073-108">Da die `Copy`-Methode in diesem Beispiel das Schlüsselwort `unsafe` verwendet, muss sie mit der Compileroption [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="ad073-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>

<span data-ttu-id="ad073-109">In diesem Beispiel werden Indizes anstelle eines zweiten nicht verwalteten Zeigers verwendet, um auf die Elemente beider Arrays zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ad073-109">This example accesses the elements of both arrays using indices rather than a second unmanaged pointer.</span></span> <span data-ttu-id="ad073-110">Die Deklaration der Zeiger `pSource` und `pTarget` heftet die Arrays an.</span><span class="sxs-lookup"><span data-stu-id="ad073-110">The declaration of the `pSource` and `pTarget` pointers pins the arrays.</span></span> <span data-ttu-id="ad073-111">Dieses Feature ist ab C# 7.3 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ad073-111">This feature is available starting with C# 7.3.</span></span>

## <a name="example"></a><span data-ttu-id="ad073-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ad073-112">Example</span></span>

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a><span data-ttu-id="ad073-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ad073-113">See also</span></span>

- [<span data-ttu-id="ad073-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ad073-114">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ad073-115">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="ad073-115">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="ad073-116">-unsafe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="ad073-116">-unsafe (C# Compiler Options)</span></span>](../../language-reference/compiler-options/unsafe-compiler-option.md)
- [<span data-ttu-id="ad073-117">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="ad073-117">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
