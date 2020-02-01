---
title: Compilerfehler und-Warnungen
description: Beschreibungen und Lösungen für Fehler und Warnungen, die F# vom Compiler ausgegeben werden
ms.date: 12/21/2019
ms.openlocfilehash: 52d94475e8b0195281d6244230c50c8f64230aeb
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76929654"
---
# <a name="f-compiler-messages"></a><span data-ttu-id="7485b-103">F#compilernachrichten</span><span class="sxs-lookup"><span data-stu-id="7485b-103">F# compiler messages</span></span>

<span data-ttu-id="7485b-104">In diesem Abschnitt werden Compilerfehler und- F# Warnungen ausführlich erläutert, die der Compiler für bestimmte Konstrukte ausgibt.</span><span class="sxs-lookup"><span data-stu-id="7485b-104">This section details compiler errors and warnings that the F# compiler will emit for certain constructs.</span></span> <span data-ttu-id="7485b-105">Die Standardsätze von Fehlern können wie folgt geändert werden:</span><span class="sxs-lookup"><span data-stu-id="7485b-105">The default sets of errors can be changed by:</span></span>

- <span data-ttu-id="7485b-106">Behandeln bestimmter Warnungen, als ob es sich um Fehler handelt, mithilfe der `-warnaserror+`-Compileroption</span><span class="sxs-lookup"><span data-stu-id="7485b-106">Treating specific warnings as if they were errors by using the `-warnaserror+` compiler option,</span></span>

- <span data-ttu-id="7485b-107">Ignorieren bestimmter Warnungen mithilfe der `-nowarn`-Compileroption</span><span class="sxs-lookup"><span data-stu-id="7485b-107">Ignoring specific warnings by using the `-nowarn` compiler option</span></span>

<span data-ttu-id="7485b-108">Wenn eine Warnung oder ein Fehler noch nicht in diesem Abschnitt aufgezeichnet wurde, fahren Sie mit dem Ende dieser Seite fort, und senden Sie Feedback, das die Anzahl oder den Text des Fehlers enthält.</span><span class="sxs-lookup"><span data-stu-id="7485b-108">If a particular warning or error is not yet recorded in this section, go to the end of this page and send feedback that includes the number or text of the error.</span></span>

## <a name="see-also"></a><span data-ttu-id="7485b-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7485b-109">See also</span></span>

- [<span data-ttu-id="7485b-110">F#Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="7485b-110">F# Compiler Options</span></span>](../compiler-options.md)
