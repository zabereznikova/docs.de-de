---
title: Compilerfehler und -warnungen
description: Beschreibungen und Lösungen für Fehler und Warnungen, die vom F#-Compiler ausgegeben werden
ms.date: 12/21/2019
ms.openlocfilehash: 58430297abe807027afdc52841d67d1233401ff1
ms.sourcegitcommit: e395fabeeea5c705d243d246fa64446839ac85b6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2021
ms.locfileid: "97856119"
---
# <a name="f-compiler-messages"></a><span data-ttu-id="77871-103">F#-Compilermeldungen</span><span class="sxs-lookup"><span data-stu-id="77871-103">F# compiler messages</span></span>

<span data-ttu-id="77871-104">In diesem Abschnitt werden Compilerfehler und -warnungen ausführlich erläutert, die der F#-Compiler für bestimmte Konstrukte ausgibt.</span><span class="sxs-lookup"><span data-stu-id="77871-104">This section details compiler errors and warnings that the F# compiler will emit for certain constructs.</span></span> <span data-ttu-id="77871-105">Die Standardfehler können wie folgt geändert werden:</span><span class="sxs-lookup"><span data-stu-id="77871-105">The default sets of errors can be changed by:</span></span>

- <span data-ttu-id="77871-106">Behandeln bestimmter Warnungen mithilfe der `-warnaserror+`-Compileroption als wären diese Fehler</span><span class="sxs-lookup"><span data-stu-id="77871-106">Treating specific warnings as if they were errors by using the `-warnaserror+` compiler option,</span></span>

- <span data-ttu-id="77871-107">Ignorieren bestimmter Warnungen mithilfe der `-nowarn`-Compileroption</span><span class="sxs-lookup"><span data-stu-id="77871-107">Ignoring specific warnings by using the `-nowarn` compiler option</span></span>

<span data-ttu-id="77871-108">Wenn eine bestimmte Warnung oder ein Fehler noch nicht in diesem Abschnitt aufgezeichnet wurde:</span><span class="sxs-lookup"><span data-stu-id="77871-108">If a particular warning or error is not yet recorded in this section:</span></span>

- <span data-ttu-id="77871-109">Scrollen Sie zum Ende dieser Seite, und senden Sie uns Feedback, einschließlich Nummer oder Text des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="77871-109">Go to the end of this page and send feedback that includes the number or text of the error, or</span></span>
- <span data-ttu-id="77871-110">Fügen Sie diesen alternativ selbst hinzu, indem Sie die Anweisungen in [create-new-fsharp-compiler-message.fsx](https://github.com/dotnet/docs/blob/master/docs/fsharp/language-reference/compiler-messages/util/create-new-fsharp-compiler-message.fsx) befolgen, und öffnen Sie einen Pull Request für dieses Repository.</span><span class="sxs-lookup"><span data-stu-id="77871-110">Add it yourself by following the instructions in [create-new-fsharp-compiler-message.fsx](https://github.com/dotnet/docs/blob/master/docs/fsharp/language-reference/compiler-messages/util/create-new-fsharp-compiler-message.fsx) and opening a pull request for this repository.</span></span>

## <a name="see-also"></a><span data-ttu-id="77871-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77871-111">See also</span></span>

- [<span data-ttu-id="77871-112">F#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="77871-112">F# Compiler Options</span></span>](../compiler-options.md)
