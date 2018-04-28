---
title: Externe Funktionen (F#)
description: Erfahren Sie, bis die f#-sprachunterstützung für aufrufende Funktionen in nativen Code.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 28e74258d91ff2d9742caa7a6c06f515cd987c0a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="external-functions"></a><span data-ttu-id="a5e9b-103">Externe Funktionen</span><span class="sxs-lookup"><span data-stu-id="a5e9b-103">External Functions</span></span>

<span data-ttu-id="a5e9b-104">Dieses Thema beschreibt die F#-sprachunterstützung für aufrufende Funktionen in nativen Code.</span><span class="sxs-lookup"><span data-stu-id="a5e9b-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="a5e9b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5e9b-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="a5e9b-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a5e9b-106">Remarks</span></span>

<span data-ttu-id="a5e9b-107">In der vorherigen Syntax *Argumente* stellt die Argumente, die bereitgestellt werden die `System.Runtime.InteropServices.DllImportAttribute` Attribut.</span><span class="sxs-lookup"><span data-stu-id="a5e9b-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="a5e9b-108">Das erste Argument ist eine Zeichenfolge, die den Namen der DLL darstellt, die diese Funktion, ohne die Erweiterung ".dll" enthält.</span><span class="sxs-lookup"><span data-stu-id="a5e9b-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="a5e9b-109">Zusätzliche Argumente können für alle öffentlichen Eigenschaften angegeben werden, die `System.Runtime.InteropServices.DllImportAttribute` Klasse, z. B. die Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="a5e9b-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="a5e9b-110">Angenommen Sie, Sie verfügen über eine systemeigene C++-DLL, die die folgenden exportierte Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="a5e9b-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="a5e9b-111">Sie können diese Funktion von F#-aufrufen, mit dem folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="a5e9b-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="a5e9b-112">Interoperabilität mit systemeigenem Code wird als bezeichnet *Plattformaufruf* und ist eine Funktion der CLR.</span><span class="sxs-lookup"><span data-stu-id="a5e9b-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="a5e9b-113">Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](../../../../docs/framework/interop/index.md).</span><span class="sxs-lookup"><span data-stu-id="a5e9b-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="a5e9b-114">Die Informationen in diesem Abschnitt gilt für f# zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a5e9b-114">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="a5e9b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5e9b-115">See Also</span></span>

[<span data-ttu-id="a5e9b-116">Funktionen</span><span class="sxs-lookup"><span data-stu-id="a5e9b-116">Functions</span></span>](index.md)
