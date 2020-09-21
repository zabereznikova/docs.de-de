---
title: Interoperabilität von Ausnahmen
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 90774b5d1b64feb34e01f48708d94f8f841a7c9d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550871"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a><span data-ttu-id="e842c-102">Arbeiten mit Interop-Ausnahmen in nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="e842c-102">Working with Interop Exceptions in Unmanaged Code</span></span>

<span data-ttu-id="e842c-103">Die Interoperabilität von Ausnahmen wegen nicht verwaltetem Code wird nur auf Windows-Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e842c-103">Unmanaged code exception interop is supported on Windows platforms only.</span></span> <span data-ttu-id="e842c-104">Auf anderen Plattformen treten Portabilitätsprobleme auf.</span><span class="sxs-lookup"><span data-stu-id="e842c-104">Portability issues arise on non-Windows platforms.</span></span> <span data-ttu-id="e842c-105">Da die UNIX-ABI über keine Definition zur Behandlung von Ausnahmen verfügt, kann verwalteter Code nicht erkennen, wie Ausnahmemechanismen im Hintergrund funktionieren.</span><span class="sxs-lookup"><span data-stu-id="e842c-105">Since the Unix ABI has no definition for exception handling, managed code can't know how exception mechanisms work under the covers.</span></span> <span data-ttu-id="e842c-106">Daher können Ausnahmen zu unvorhersehbarem Verhalten und Abstürzen führen.</span><span class="sxs-lookup"><span data-stu-id="e842c-106">Therefore, exceptions can end up resulting in unpredictable behaviors and crashes.</span></span>

## <a name="setjmplongjmp-behaviors"></a><span data-ttu-id="e842c-107">Setjmp/Longjmp-Verhalten</span><span class="sxs-lookup"><span data-stu-id="e842c-107">Setjmp/Longjmp Behaviors</span></span>

<span data-ttu-id="e842c-108">Die Interoperabilität mit den C-Funktionen `setjmp` und `longjmp` wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e842c-108">Interop with `setjmp` and `longjmp` C functions is not supported.</span></span> <span data-ttu-id="e842c-109">Sie können `longjmp` nicht zum Überspringen von verwalteten Frames verwenden.</span><span class="sxs-lookup"><span data-stu-id="e842c-109">You can't use `longjmp` to skip over managed frames.</span></span>

<span data-ttu-id="e842c-110">Weitere Informationen finden Sie in der [longjmp-Dokumentation](/cpp/c-runtime-library/reference/longjmp).</span><span class="sxs-lookup"><span data-stu-id="e842c-110">For more information, see [longjmp documentation](/cpp/c-runtime-library/reference/longjmp).</span></span>

## <a name="see-also"></a><span data-ttu-id="e842c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e842c-111">See also</span></span>

- [<span data-ttu-id="e842c-112">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="e842c-112">Exceptions</span></span>](index.md)
- [<span data-ttu-id="e842c-113">Interoperabilität mit nativen Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="e842c-113">Interop with Native Libraries</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
