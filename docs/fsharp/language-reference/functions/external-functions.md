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

Interoperabilität mit systemeigenem Code wird als bezeichnet *Plattformaufruf* und ist eine Funktion der CLR. Weitere Informationen finden Sie unter [Interoperation mit nicht verwaltetem Code](https://msdn.microsoft.com/library/sd10k43k.aspx). Die Informationen in diesem Abschnitt gilt für f# zur Verfügung.


## <a name="see-also"></a>Siehe auch

[Funktionen](index.md)
