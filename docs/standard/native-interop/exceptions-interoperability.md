---
title: Interoperabilität von Ausnahmen
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 2aff71e97e1be0dbb584f4fe43c322cea86d2480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794621"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a><span data-ttu-id="63ebc-102">Arbeiten mit Interop-Ausnahmen in nicht verwaltetem Code</span><span class="sxs-lookup"><span data-stu-id="63ebc-102">Working with Interop Exceptions in Unmanaged Code</span></span>

<span data-ttu-id="63ebc-103">Die Interoperabilität von Ausnahmen wegen nicht verwaltetem Code wird nur auf Windows-Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63ebc-103">Unmanaged code exception interop is supported on Windows platforms only.</span></span> <span data-ttu-id="63ebc-104">Auf anderen Plattformen treten Portabilitätsprobleme auf.</span><span class="sxs-lookup"><span data-stu-id="63ebc-104">Portability issues arise on non-Windows platforms.</span></span> <span data-ttu-id="63ebc-105">Da die UNIX-ABI über keine Definition zur Behandlung von Ausnahmen verfügt, kann verwalteter Code nicht erkennen, wie Ausnahmemechanismen im Hintergrund funktionieren.</span><span class="sxs-lookup"><span data-stu-id="63ebc-105">Since the Unix ABI has no definition for exception handling, managed code can't know how exception mechanisms work under the covers.</span></span> <span data-ttu-id="63ebc-106">Daher können Ausnahmen zu unvorhersehbarem Verhalten und Abstürzen führen.</span><span class="sxs-lookup"><span data-stu-id="63ebc-106">Therefore, exceptions can end up resulting in unpredictable behaviors and crashes.</span></span>

## <a name="setjmplongjmp-behaviors"></a><span data-ttu-id="63ebc-107">Setjmp/Longjmp-Verhalten</span><span class="sxs-lookup"><span data-stu-id="63ebc-107">Setjmp/Longjmp Behaviors</span></span>

<span data-ttu-id="63ebc-108">Die Interoperabilität mit den C-Funktionen `setjmp` und `longjmp` wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63ebc-108">Interop with `setjmp` and `longjmp` C functions is not supported.</span></span> <span data-ttu-id="63ebc-109">Sie können `longjmp` nicht zum Überspringen von verwalteten Frames verwenden.</span><span class="sxs-lookup"><span data-stu-id="63ebc-109">You can't use `longjmp` to skip over managed frames.</span></span>

<span data-ttu-id="63ebc-110">Weitere Informationen finden Sie in der [longjmp-Dokumentation](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).</span><span class="sxs-lookup"><span data-stu-id="63ebc-110">For more information, see [longjmp documentation](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).</span></span>

## <a name="see-also"></a><span data-ttu-id="63ebc-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63ebc-111">See also</span></span>

- [<span data-ttu-id="63ebc-112">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="63ebc-112">Exceptions</span></span>](index.md)
- [<span data-ttu-id="63ebc-113">Interoperabilität mit nativen Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="63ebc-113">Interop with Native Libraries</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
