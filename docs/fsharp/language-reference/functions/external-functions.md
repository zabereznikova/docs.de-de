---
title: Externe Funktionen
description: Erfahren Sie mehr über die F# sprachunterstützung für das Aufrufen von Funktionen in systemeigenen Code.
ms.date: 05/16/2016
ms.openlocfilehash: 73e38d8942bfc8ddb3c51d126d7678e84903326b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642046"
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
