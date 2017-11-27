---
title: Einstiegspunkt (F#)
description: "Erfahren Sie, wie ein f#-Programms Einstiegspunkt fest, die als eine ausführbare Datei kompiliert wird, in dem Ausführung formal beginnt."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 91455443-ff9d-4510-a7e9-1560bdcd0bb0
ms.openlocfilehash: 685fd4da67119aa5fcaaffd142a0a17c8f5dc7f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="entry-point"></a><span data-ttu-id="d0bf4-104">Einstiegspunkt</span><span class="sxs-lookup"><span data-stu-id="d0bf4-104">Entry Point</span></span>

<span data-ttu-id="d0bf4-105">Dieses Thema beschreibt die Methode, mit denen Sie den Einstiegspunkt auf einem F#-Programm festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-105">This topic describes the method that you use to set the entry point to an F# program.</span></span>


## <a name="syntax"></a><span data-ttu-id="d0bf4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0bf4-106">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="d0bf4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d0bf4-107">Remarks</span></span>
<span data-ttu-id="d0bf4-108">In der vorherigen Syntax *Let funktionsbindung* ist die Definition einer Funktion in einer `let` Bindung.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-108">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="d0bf4-109">Der Einstiegspunkt an ein Programm, das kompiliert wird, wie eine ausführbare Datei handelt, in dem Ausführung formal beginnt.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-109">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="d0bf4-110">Geben Sie den Einstiegspunkt für eine f#-Anwendung, durch Anwenden der `EntryPoint` -Attribut auf des Programms `main` Funktion.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-110">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="d0bf4-111">Diese Funktion (erstellt mit einer `let` Bindung) muss die letzte Funktion in der letzten kompilierten Datei sein.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-111">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="d0bf4-112">Die letzte kompilierte Datei ist die letzte Datei im Projekt oder die letzte Datei, die an der Befehlszeile übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-112">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="d0bf4-113">Die Einstiegspunktfunktion weist den Typ `string array -> int`.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-113">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="d0bf4-114">Argumente in der Befehlszeile übergeben werden, um die `main` -Funktion in das Array von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-114">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="d0bf4-115">Das erste Element des Arrays ist das erste Argument; der Name der ausführbaren Datei ist nicht im Array enthalten, da es in einigen anderen Sprachen ist.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-115">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="d0bf4-116">Der zurückgegebene Wert wird als der Exitcode für den Prozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-116">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="d0bf4-117">0 (null) gibt in der Regel die erfolgreiche Ausführung; Werte ungleich Null geben einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-117">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="d0bf4-118">Es gibt keine Konvention für die spezifische Bedeutung des Rückgabecodes ungleich null; die Bedeutung des Rückgabecodes sind anwendungsspezifisch.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-118">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="d0bf4-119">Das folgende Beispiel veranschaulicht eine einfache `main` Funktion.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-119">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="d0bf4-120">Wenn dieser Code ausgeführt wird, mit der Befehlszeile `EntryPoint.exe 1 2 3`, die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-120">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="d0bf4-121">Implizite Einstiegspunkt</span><span class="sxs-lookup"><span data-stu-id="d0bf4-121">Implicit Entry Point</span></span>
<span data-ttu-id="d0bf4-122">Wenn ein Programm hat keine **EntryPoint** -Attribut, das den Einstiegspunkt der obersten Ebene Bindungen in der letzten Datei zu kompilierenden gibt explizit an als Einstiegspunkt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d0bf4-122">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>


## <a name="see-also"></a><span data-ttu-id="d0bf4-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0bf4-123">See Also</span></span>
[<span data-ttu-id="d0bf4-124">Funktionen</span><span class="sxs-lookup"><span data-stu-id="d0bf4-124">Functions</span></span>](index.md)

[<span data-ttu-id="d0bf4-125">let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="d0bf4-125">let Bindings</span></span>](let-bindings.md)
