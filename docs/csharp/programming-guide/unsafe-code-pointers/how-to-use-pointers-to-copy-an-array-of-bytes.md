---
title: 'Vorgehensweise: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie Zeiger verwenden, um ein Array aus Bytes zu kopieren. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: 70ab1441d25ea69afb2244bd94bd404a3e32838d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381787"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes-c-programming-guide"></a><span data-ttu-id="8546d-104">Vorgehensweise: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierleitfaden)</span><span class="sxs-lookup"><span data-stu-id="8546d-104">How to use pointers to copy an array of bytes (C# Programming Guide)</span></span>

<span data-ttu-id="8546d-105">In folgendem Beispiel werden Zeiger verwendet, um Bytes aus einem Array in ein anderes zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="8546d-105">The following example uses pointers to copy bytes from one array to another.</span></span>

<span data-ttu-id="8546d-106">In diesem Beispiel wird das Schlüsselwort [unsafe](../../language-reference/keywords/unsafe.md) verwendet, mit dem Sie Zeiger in der `Copy`-Methode verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8546d-106">This example uses the [unsafe](../../language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="8546d-107">Die Anweisung [fixed](../../language-reference/keywords/fixed-statement.md) wird verwendet, um Zeiger auf das Quell- und Zielarray zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="8546d-107">The [fixed](../../language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="8546d-108">Diese `fixed`-Anweisung *heftet* den Speicherort des Quell- und Zielarrays im Speicher an, damit diese während der automatischen Speicherbereinigung nicht verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="8546d-108">The `fixed` statement *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="8546d-109">Die Speicherblöcke der Arrays werden gelöst, wenn der `fixed`-Block abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="8546d-109">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="8546d-110">Da die `Copy`-Methode in diesem Beispiel das Schlüsselwort `unsafe` verwendet, muss sie mit der Compileroption [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="8546d-110">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>

<span data-ttu-id="8546d-111">In diesem Beispiel werden Indizes anstelle eines zweiten nicht verwalteten Zeigers verwendet, um auf die Elemente beider Arrays zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="8546d-111">This example accesses the elements of both arrays using indices rather than a second unmanaged pointer.</span></span> <span data-ttu-id="8546d-112">Die Deklaration der Zeiger `pSource` und `pTarget` heftet die Arrays an.</span><span class="sxs-lookup"><span data-stu-id="8546d-112">The declaration of the `pSource` and `pTarget` pointers pins the arrays.</span></span> <span data-ttu-id="8546d-113">Dieses Feature ist ab C# 7.3 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8546d-113">This feature is available starting with C# 7.3.</span></span>

## <a name="example"></a><span data-ttu-id="8546d-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8546d-114">Example</span></span>

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a><span data-ttu-id="8546d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8546d-115">See also</span></span>

- [<span data-ttu-id="8546d-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="8546d-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8546d-117">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="8546d-117">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="8546d-118">-unsafe (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="8546d-118">-unsafe (C# Compiler Options)</span></span>](../../language-reference/compiler-options/unsafe-compiler-option.md)
- [<span data-ttu-id="8546d-119">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="8546d-119">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
