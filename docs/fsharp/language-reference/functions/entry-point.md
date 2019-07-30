---
title: Einstiegspunkt
description: Erfahren Sie, wie eine F#-Programm Einstiegspunkt fest, die als ausführbare Datei kompiliert wird, in dem Ausführung formal beginnt.
ms.date: 05/16/2016
ms.openlocfilehash: 5e13416131d4dfd22583439fedf51f18f7a461da
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630524"
---
# <a name="entry-point"></a><span data-ttu-id="0e538-103">Einstiegspunkt</span><span class="sxs-lookup"><span data-stu-id="0e538-103">Entry Point</span></span>

<span data-ttu-id="0e538-104">In diesem Thema wird die-Methode beschrieben, mit der Sie den Einstiegspunkt F# auf ein-Programm festlegen.</span><span class="sxs-lookup"><span data-stu-id="0e538-104">This topic describes the method that you use to set the entry point to an F# program.</span></span>

## <a name="syntax"></a><span data-ttu-id="0e538-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e538-105">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="0e538-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e538-106">Remarks</span></span>

<span data-ttu-id="0e538-107">In der vorherigen Syntax ist *let-function-binding* die Definition einer Funktion in einer `let` Bindung.</span><span class="sxs-lookup"><span data-stu-id="0e538-107">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="0e538-108">Der Einstiegspunkt zu einem Programm, das als ausführbare Datei kompiliert wird, ist die formale Ausführung.</span><span class="sxs-lookup"><span data-stu-id="0e538-108">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="0e538-109">Sie geben den Einstiegspunkt für eine F# Anwendung an, indem `EntryPoint` Sie das- `main` Attribut auf die Funktion des Programms anwenden.</span><span class="sxs-lookup"><span data-stu-id="0e538-109">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="0e538-110">Diese Funktion (erstellt mithilfe einer `let` -Bindung) muss die letzte Funktion in der letzten kompilierten Datei sein.</span><span class="sxs-lookup"><span data-stu-id="0e538-110">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="0e538-111">Die letzte kompilierte Datei ist die letzte Datei im Projekt oder die letzte Datei, die an die Befehlszeile übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="0e538-111">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="0e538-112">Die Einstiegspunkt Funktion weist den `string array -> int`Typ auf.</span><span class="sxs-lookup"><span data-stu-id="0e538-112">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="0e538-113">Die Argumente, die in der Befehlszeile angegeben werden, `main` werden an die Funktion im Zeichen folgen Array weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="0e538-113">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="0e538-114">Das erste Element des Arrays ist das erste Argument. der Name der ausführbaren Datei ist nicht im Array enthalten, da Sie in einigen anderen Sprachen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="0e538-114">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="0e538-115">Der Rückgabewert wird als Exitcode für den Prozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="0e538-115">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="0e538-116">NULL zeigt normalerweise den Erfolg an. Werte ungleich 0 (null) geben einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="0e538-116">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="0e538-117">Es gibt keine Konvention für die jeweilige Bedeutung von Rückgabecodes, die nicht NULL sind. die Bedeutungen der Rückgabecodes sind anwendungsspezifisch.</span><span class="sxs-lookup"><span data-stu-id="0e538-117">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="0e538-118">Im folgenden Beispiel wird eine einfache `main` Funktion veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0e538-118">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="0e538-119">Wenn dieser Code mit der Befehlszeile `EntryPoint.exe 1 2 3`ausgeführt wird, lautet die Ausgabe wie folgt.</span><span class="sxs-lookup"><span data-stu-id="0e538-119">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="0e538-120">Impliziter Einstiegspunkt</span><span class="sxs-lookup"><span data-stu-id="0e538-120">Implicit Entry Point</span></span>

<span data-ttu-id="0e538-121">Wenn ein Programm über kein **entryPoint** -Attribut verfügt, das den Einstiegspunkt explizit angibt, werden die Bindungen auf oberster Ebene in der letzten zu kompilierenden Datei als Einstiegspunkt verwendet.</span><span class="sxs-lookup"><span data-stu-id="0e538-121">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e538-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e538-122">See also</span></span>

- [<span data-ttu-id="0e538-123">Funktionen</span><span class="sxs-lookup"><span data-stu-id="0e538-123">Functions</span></span>](index.md)
- [<span data-ttu-id="0e538-124">let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="0e538-124">let Bindings</span></span>](let-bindings.md)
