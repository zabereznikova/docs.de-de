---
title: Externe Funktionen (F#)
description: "Erfahren Sie, bis die f#-sprachunterstützung für aufrufende Funktionen in nativen Code."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c26b6124-ceaa-471c-9dc9-861b4dfa332a
ms.openlocfilehash: 4f525b2b750c2ce42230c61aa0e72f957739b206
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="external-functions"></a><span data-ttu-id="8a153-104">Externe Funktionen</span><span class="sxs-lookup"><span data-stu-id="8a153-104">External Functions</span></span>

<span data-ttu-id="8a153-105">Dieses Thema beschreibt die F#-sprachunterstützung für aufrufende Funktionen in nativen Code.</span><span class="sxs-lookup"><span data-stu-id="8a153-105">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a153-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a153-106">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="8a153-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a153-107">Remarks</span></span>

<span data-ttu-id="8a153-108">In der vorherigen Syntax *Argumente* stellt die Argumente, die bereitgestellt werden die `System.Runtime.InteropServices.DllImportAttribute` Attribut.</span><span class="sxs-lookup"><span data-stu-id="8a153-108">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="8a153-109">Das erste Argument ist eine Zeichenfolge, die den Namen der DLL darstellt, die diese Funktion, ohne die Erweiterung ".dll" enthält.</span><span class="sxs-lookup"><span data-stu-id="8a153-109">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="8a153-110">Zusätzliche Argumente können für alle öffentlichen Eigenschaften angegeben werden, die `System.Runtime.InteropServices.DllImportAttribute` Klasse, z. B. die Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="8a153-110">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="8a153-111">Angenommen Sie, Sie verfügen über eine systemeigene C++-DLL, die die folgenden exportierte Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="8a153-111">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="8a153-112">Sie können diese Funktion von F#-aufrufen, mit dem folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="8a153-112">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="8a153-113">Interoperabilität mit systemeigenem Code wird als bezeichnet *Plattformaufruf* und ist eine Funktion der CLR.</span><span class="sxs-lookup"><span data-stu-id="8a153-113">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="8a153-114">Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](https://msdn.microsoft.com/library/sd10k43k.aspx).</span><span class="sxs-lookup"><span data-stu-id="8a153-114">For more information, see [Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k.aspx).</span></span> <span data-ttu-id="8a153-115">Die Informationen in diesem Abschnitt gilt für f# zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8a153-115">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="8a153-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a153-116">See Also</span></span>

[<span data-ttu-id="8a153-117">Funktionen</span><span class="sxs-lookup"><span data-stu-id="8a153-117">Functions</span></span>](index.md)
