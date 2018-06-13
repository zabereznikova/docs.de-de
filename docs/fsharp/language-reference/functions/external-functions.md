---
title: Externe Funktionen (F#)
description: Erfahren Sie, bis die f#-sprachunterstützung für aufrufende Funktionen in nativen Code.
ms.date: 05/16/2016
ms.openlocfilehash: 398697c5e0deab7f8d81ec5198ab1918bd865e13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564481"
---
# <a name="external-functions"></a><span data-ttu-id="f82dc-103">Externe Funktionen</span><span class="sxs-lookup"><span data-stu-id="f82dc-103">External Functions</span></span>

<span data-ttu-id="f82dc-104">Dieses Thema beschreibt die F#-sprachunterstützung für aufrufende Funktionen in nativen Code.</span><span class="sxs-lookup"><span data-stu-id="f82dc-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="f82dc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f82dc-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="f82dc-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f82dc-106">Remarks</span></span>

<span data-ttu-id="f82dc-107">In der vorherigen Syntax *Argumente* stellt die Argumente, die bereitgestellt werden die `System.Runtime.InteropServices.DllImportAttribute` Attribut.</span><span class="sxs-lookup"><span data-stu-id="f82dc-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="f82dc-108">Das erste Argument ist eine Zeichenfolge, die den Namen der DLL darstellt, die diese Funktion, ohne die Erweiterung ".dll" enthält.</span><span class="sxs-lookup"><span data-stu-id="f82dc-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="f82dc-109">Zusätzliche Argumente können für alle öffentlichen Eigenschaften angegeben werden, die `System.Runtime.InteropServices.DllImportAttribute` Klasse, z. B. die Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="f82dc-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="f82dc-110">Angenommen Sie, Sie verfügen über eine systemeigene C++-DLL, die die folgenden exportierte Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="f82dc-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="f82dc-111">Sie können diese Funktion von F#-aufrufen, mit dem folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="f82dc-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="f82dc-112">Interoperabilität mit systemeigenem Code wird als bezeichnet *Plattformaufruf* und ist eine Funktion der CLR.</span><span class="sxs-lookup"><span data-stu-id="f82dc-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="f82dc-113">Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](../../../../docs/framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="f82dc-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="f82dc-114">Die Informationen in diesem Abschnitt gilt für f# zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f82dc-114">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="f82dc-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f82dc-115">See Also</span></span>

[<span data-ttu-id="f82dc-116">Funktionen</span><span class="sxs-lookup"><span data-stu-id="f82dc-116">Functions</span></span>](index.md)
