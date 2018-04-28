---
title: Einstiegspunkt (F#)
description: Erfahren Sie, wie ein f#-Programms Einstiegspunkt fest, die als eine ausführbare Datei kompiliert wird, in dem Ausführung formal beginnt.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 42e5fe7f85285f990ef92e9791ed5bdfacb85059
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="entry-point"></a><span data-ttu-id="33362-103">Einstiegspunkt</span><span class="sxs-lookup"><span data-stu-id="33362-103">Entry Point</span></span>

<span data-ttu-id="33362-104">Dieses Thema beschreibt die Methode, mit denen Sie den Einstiegspunkt auf einem F#-Programm festgelegt.</span><span class="sxs-lookup"><span data-stu-id="33362-104">This topic describes the method that you use to set the entry point to an F# program.</span></span>


## <a name="syntax"></a><span data-ttu-id="33362-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="33362-105">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="33362-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33362-106">Remarks</span></span>
<span data-ttu-id="33362-107">In der vorherigen Syntax *Let funktionsbindung* ist die Definition einer Funktion in einer `let` Bindung.</span><span class="sxs-lookup"><span data-stu-id="33362-107">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="33362-108">Der Einstiegspunkt an ein Programm, das kompiliert wird, wie eine ausführbare Datei handelt, in dem Ausführung formal beginnt.</span><span class="sxs-lookup"><span data-stu-id="33362-108">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="33362-109">Geben Sie den Einstiegspunkt für eine f#-Anwendung, durch Anwenden der `EntryPoint` -Attribut auf des Programms `main` Funktion.</span><span class="sxs-lookup"><span data-stu-id="33362-109">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="33362-110">Diese Funktion (erstellt mit einer `let` Bindung) muss die letzte Funktion in der letzten kompilierten Datei sein.</span><span class="sxs-lookup"><span data-stu-id="33362-110">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="33362-111">Die letzte kompilierte Datei ist die letzte Datei im Projekt oder die letzte Datei, die an der Befehlszeile übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="33362-111">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="33362-112">Die Einstiegspunktfunktion weist den Typ `string array -> int`.</span><span class="sxs-lookup"><span data-stu-id="33362-112">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="33362-113">Argumente in der Befehlszeile übergeben werden, um die `main` -Funktion in das Array von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="33362-113">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="33362-114">Das erste Element des Arrays ist das erste Argument; der Name der ausführbaren Datei ist nicht im Array enthalten, da es in einigen anderen Sprachen ist.</span><span class="sxs-lookup"><span data-stu-id="33362-114">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="33362-115">Der zurückgegebene Wert wird als der Exitcode für den Prozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="33362-115">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="33362-116">0 (null) gibt in der Regel die erfolgreiche Ausführung; Werte ungleich Null geben einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="33362-116">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="33362-117">Es gibt keine Konvention für die spezifische Bedeutung des Rückgabecodes ungleich null; die Bedeutung des Rückgabecodes sind anwendungsspezifisch.</span><span class="sxs-lookup"><span data-stu-id="33362-117">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="33362-118">Das folgende Beispiel veranschaulicht eine einfache `main` Funktion.</span><span class="sxs-lookup"><span data-stu-id="33362-118">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="33362-119">Wenn dieser Code ausgeführt wird, mit der Befehlszeile `EntryPoint.exe 1 2 3`, die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="33362-119">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="33362-120">Implizite Einstiegspunkt</span><span class="sxs-lookup"><span data-stu-id="33362-120">Implicit Entry Point</span></span>
<span data-ttu-id="33362-121">Wenn ein Programm hat keine **EntryPoint** -Attribut, das den Einstiegspunkt der obersten Ebene Bindungen in der letzten Datei zu kompilierenden gibt explizit an als Einstiegspunkt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33362-121">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>


## <a name="see-also"></a><span data-ttu-id="33362-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33362-122">See Also</span></span>
[<span data-ttu-id="33362-123">Funktionen</span><span class="sxs-lookup"><span data-stu-id="33362-123">Functions</span></span>](index.md)

[<span data-ttu-id="33362-124">let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="33362-124">let Bindings</span></span>](let-bindings.md)
