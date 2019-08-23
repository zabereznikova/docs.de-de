---
title: Externe Funktionen
description: Erfahren Sie mehr F# über die Sprachunterstützung für das Aufrufen von Funktionen in nativem Code.
ms.date: 05/16/2016
ms.openlocfilehash: 3c8edaba25e07b6ca2c44a58c4b55dc98a13b4fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968732"
---
# <a name="external-functions"></a><span data-ttu-id="ea676-103">Externe Funktionen</span><span class="sxs-lookup"><span data-stu-id="ea676-103">External Functions</span></span>

<span data-ttu-id="ea676-104">In diesem Thema F# wird die Sprachunterstützung für das Aufrufen von Funktionen in nativem Code beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ea676-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="ea676-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea676-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="ea676-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea676-106">Remarks</span></span>

<span data-ttu-id="ea676-107">In der vorherigen Syntax stellen *Argumente* Argumente dar, die für das `System.Runtime.InteropServices.DllImportAttribute` Attribut bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ea676-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="ea676-108">Das erste Argument ist eine Zeichenfolge, die den Namen der DLL darstellt, die diese Funktion enthält, ohne die DLL-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="ea676-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="ea676-109">Für jede der öffentlichen Eigenschaften der `System.Runtime.InteropServices.DllImportAttribute` Klasse, z. b. die Aufruf Konvention, können zusätzliche Argumente angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ea676-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="ea676-110">Angenommen, Sie verfügen über C++ eine native dll, die die folgende exportierte Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="ea676-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="ea676-111">Diese Funktion kann mithilfe des folgenden F# Codes aus aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ea676-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="ea676-112">Interoperabilität mit nativem Code wird als *Platt Form Aufruf* bezeichnet und ist eine Funktion der CLR.</span><span class="sxs-lookup"><span data-stu-id="ea676-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="ea676-113">Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](../../../framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="ea676-113">For more information, see [Interoperating with Unmanaged Code](../../../framework/interop/index.md).</span></span> <span data-ttu-id="ea676-114">Die Informationen in diesem Abschnitt gelten für F#.</span><span class="sxs-lookup"><span data-stu-id="ea676-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="ea676-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea676-115">See also</span></span>

- [<span data-ttu-id="ea676-116">Funktionen</span><span class="sxs-lookup"><span data-stu-id="ea676-116">Functions</span></span>](index.md)
