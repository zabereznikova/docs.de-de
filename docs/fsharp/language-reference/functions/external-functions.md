---
title: Externe Funktionen (F#)
description: Erfahren Sie, bis die f#-sprachunterstützung für aufrufende Funktionen in nativen Code.
ms.date: 05/16/2016
ms.openlocfilehash: 398697c5e0deab7f8d81ec5198ab1918bd865e13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="external-functions"></a>Externe Funktionen

Dieses Thema beschreibt die F#-sprachunterstützung für aufrufende Funktionen in nativen Code.

## <a name="syntax"></a>Syntax

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax *Argumente* stellt die Argumente, die bereitgestellt werden die `System.Runtime.InteropServices.DllImportAttribute` Attribut. Das erste Argument ist eine Zeichenfolge, die den Namen der DLL darstellt, die diese Funktion, ohne die Erweiterung ".dll" enthält. Zusätzliche Argumente können für alle öffentlichen Eigenschaften angegeben werden, die `System.Runtime.InteropServices.DllImportAttribute` Klasse, z. B. die Aufrufkonvention.

Angenommen Sie, Sie verfügen über eine systemeigene C++-DLL, die die folgenden exportierte Funktion enthält.

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

Sie können diese Funktion von F#-aufrufen, mit dem folgenden Code.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

Interoperabilität mit systemeigenem Code wird als bezeichnet *Plattformaufruf* und ist eine Funktion der CLR. Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](../../../../docs/framework/interop/index.md). Die Informationen in diesem Abschnitt gilt für f# zur Verfügung.


## <a name="see-also"></a>Siehe auch

[Funktionen](index.md)
