---
title: Externe Funktionen
description: Erfahren Sie mehr über die F# sprachunterstützung für das Aufrufen von Funktionen in systemeigenen Code.
ms.date: 05/16/2016
ms.openlocfilehash: 86ea78844fb812361233f8360c377465d83be203
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611725"
---
# <a name="external-functions"></a><span data-ttu-id="66787-103">Externe Funktionen</span><span class="sxs-lookup"><span data-stu-id="66787-103">External Functions</span></span>

<span data-ttu-id="66787-104">In diesem Thema wird beschrieben, F# sprachunterstützung für das Aufrufen von Funktionen in systemeigenen Code.</span><span class="sxs-lookup"><span data-stu-id="66787-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="66787-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="66787-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="66787-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="66787-106">Remarks</span></span>

<span data-ttu-id="66787-107">In der vorherigen Syntax wird *Argumente* stellt die Argumente, die an sind die `System.Runtime.InteropServices.DllImportAttribute` Attribut.</span><span class="sxs-lookup"><span data-stu-id="66787-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="66787-108">Das erste Argument ist eine Zeichenfolge mit dem Namen der DLL, die dieser Funktion, ohne die .dll-Erweiterung enthält.</span><span class="sxs-lookup"><span data-stu-id="66787-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="66787-109">Zusätzliche Argumente angegeben werden können, für alle öffentlichen Eigenschaften des der `System.Runtime.InteropServices.DllImportAttribute` Klasse, z. B. die Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="66787-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="66787-110">Angenommen Sie, Sie haben eine systemeigene C++-DLL, die die folgende exportierte Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="66787-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="66787-111">Sie können diese Funktion aus aufrufen F# mithilfe des folgenden Codes.</span><span class="sxs-lookup"><span data-stu-id="66787-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="66787-112">Interoperabilität mit systemeigenem Code wird als bezeichnet *Plattformaufruf* ist ein Feature der CLR.</span><span class="sxs-lookup"><span data-stu-id="66787-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="66787-113">Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](../../../../docs/framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="66787-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="66787-114">Die Informationen in diesem Abschnitt gilt für F#.</span><span class="sxs-lookup"><span data-stu-id="66787-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="66787-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66787-115">See also</span></span>

- [<span data-ttu-id="66787-116">Funktionen</span><span class="sxs-lookup"><span data-stu-id="66787-116">Functions</span></span>](index.md)