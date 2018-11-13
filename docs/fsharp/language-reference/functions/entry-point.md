---
title: Einstiegspunkt (F#)
description: Erfahren Sie, wie eine F#-Programm Einstiegspunkt fest, die als ausführbare Datei kompiliert wird, in dem Ausführung formal beginnt.
ms.date: 05/16/2016
ms.openlocfilehash: 298500931d49c891a7a243295333df3a9f5d413e
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "45698381"
---
# <a name="entry-point"></a><span data-ttu-id="4ac25-103">Einstiegspunkt</span><span class="sxs-lookup"><span data-stu-id="4ac25-103">Entry Point</span></span>

<span data-ttu-id="4ac25-104">In diesem Thema wird beschrieben, die Methode, die Sie verwenden, um den Einstiegspunkt auf einem F#-Programm festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="4ac25-104">This topic describes the method that you use to set the entry point to an F# program.</span></span>

## <a name="syntax"></a><span data-ttu-id="4ac25-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ac25-105">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="4ac25-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4ac25-106">Remarks</span></span>

<span data-ttu-id="4ac25-107">In der vorherigen Syntax *Let-Funktion-Bindung* ist die Definition einer Funktion in einer `let` Bindung.</span><span class="sxs-lookup"><span data-stu-id="4ac25-107">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="4ac25-108">Der Einstiegspunkt an ein Programm, das kompiliert wird, wie eine ausführbare Datei handelt, in dem Ausführung formal beginnt.</span><span class="sxs-lookup"><span data-stu-id="4ac25-108">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="4ac25-109">Sie geben den Einstiegspunkt für eine F#-Anwendung durch Anwenden der `EntryPoint` Attribut des Programms `main` Funktion.</span><span class="sxs-lookup"><span data-stu-id="4ac25-109">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="4ac25-110">Diese Funktion (erstellt mit einem `let` Bindung) muss die letzte Funktion in der letzten kompilierten Datei.</span><span class="sxs-lookup"><span data-stu-id="4ac25-110">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="4ac25-111">Die letzte kompilierte Datei ist die letzte Datei im Projekt oder die letzte Datei, die an der Befehlszeile übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="4ac25-111">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="4ac25-112">Die Einstiegspunktfunktion weist den Typ `string array -> int`.</span><span class="sxs-lookup"><span data-stu-id="4ac25-112">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="4ac25-113">Die Argumente, die in der Befehlszeile angegeben werden übergeben die `main` -Funktion in das Array von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="4ac25-113">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="4ac25-114">Das erste Element des Arrays ist das erste Argument. der Name der ausführbaren Datei ist nicht im Array enthalten, da es in einigen anderen Sprachen ist.</span><span class="sxs-lookup"><span data-stu-id="4ac25-114">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="4ac25-115">Der zurückgegebene Wert wird als Exitcode für den Prozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ac25-115">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="4ac25-116">0 (null) gibt in der Regel Erfolg; ungleich NULL-Werte geben einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="4ac25-116">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="4ac25-117">Es gibt keine Konvention für die spezifische Bedeutung des Rückgabecodes für ungleich NULL. die Bedeutung des Rückgabecodes sind anwendungsspezifisch.</span><span class="sxs-lookup"><span data-stu-id="4ac25-117">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="4ac25-118">Das folgende Beispiel veranschaulicht eine einfache `main` Funktion.</span><span class="sxs-lookup"><span data-stu-id="4ac25-118">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="4ac25-119">Wenn dieser Code ausgeführt wird, über die Befehlszeile `EntryPoint.exe 1 2 3`, die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="4ac25-119">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="4ac25-120">Impliziter Einstiegspunkt</span><span class="sxs-lookup"><span data-stu-id="4ac25-120">Implicit Entry Point</span></span>

<span data-ttu-id="4ac25-121">Wenn ein Programm hat keine **EntryPoint** -Attribut, das explizit angibt, den Einstiegspunkt, der die Bindungen auf oberster Ebene in der letzten Datei kompiliert werden, werden als Einstiegspunkt verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ac25-121">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ac25-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ac25-122">See also</span></span>

- [<span data-ttu-id="4ac25-123">Funktionen</span><span class="sxs-lookup"><span data-stu-id="4ac25-123">Functions</span></span>](index.md)
- [<span data-ttu-id="4ac25-124">let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="4ac25-124">let Bindings</span></span>](let-bindings.md)
