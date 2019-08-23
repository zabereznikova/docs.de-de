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
# <a name="external-functions"></a>Externe Funktionen

In diesem Thema F# wird die Sprachunterstützung für das Aufrufen von Funktionen in nativem Code beschrieben.

## <a name="syntax"></a>Syntax

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax stellen *Argumente* Argumente dar, die für das `System.Runtime.InteropServices.DllImportAttribute` Attribut bereitgestellt werden. Das erste Argument ist eine Zeichenfolge, die den Namen der DLL darstellt, die diese Funktion enthält, ohne die DLL-Erweiterung. Für jede der öffentlichen Eigenschaften der `System.Runtime.InteropServices.DllImportAttribute` Klasse, z. b. die Aufruf Konvention, können zusätzliche Argumente angegeben werden.

Angenommen, Sie verfügen über C++ eine native dll, die die folgende exportierte Funktion enthält.

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

Diese Funktion kann mithilfe des folgenden F# Codes aus aufgerufen werden.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

Interoperabilität mit nativem Code wird als *Platt Form Aufruf* bezeichnet und ist eine Funktion der CLR. Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](../../../framework/interop/index.md). Die Informationen in diesem Abschnitt gelten für F#.

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)
