---
title: Externe Funktionen
description: Erfahren Sie mehr über die F# sprachunterstützung für das Aufrufen von Funktionen in systemeigenen Code.
ms.date: 05/16/2016
ms.openlocfilehash: 86ea78844fb812361233f8360c377465d83be203
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934627"
---
# <a name="external-functions"></a>Externe Funktionen

In diesem Thema wird beschrieben, F# sprachunterstützung für das Aufrufen von Funktionen in systemeigenen Code.

## <a name="syntax"></a>Syntax

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax wird *Argumente* stellt die Argumente, die an sind die `System.Runtime.InteropServices.DllImportAttribute` Attribut. Das erste Argument ist eine Zeichenfolge mit dem Namen der DLL, die dieser Funktion, ohne die .dll-Erweiterung enthält. Zusätzliche Argumente angegeben werden können, für alle öffentlichen Eigenschaften des der `System.Runtime.InteropServices.DllImportAttribute` Klasse, z. B. die Aufrufkonvention.

Angenommen Sie, Sie haben eine systemeigene C++-DLL, die die folgende exportierte Funktion enthält.

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

Sie können diese Funktion aus aufrufen F# mithilfe des folgenden Codes.

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

Interoperabilität mit systemeigenem Code wird als bezeichnet *Plattformaufruf* ist ein Feature der CLR. Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](../../../../docs/framework/interop/index.md). Die Informationen in diesem Abschnitt gilt für F#.

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)