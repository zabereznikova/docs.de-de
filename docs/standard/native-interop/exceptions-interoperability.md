---
title: Interoperabilität von Ausnahmen
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 90774b5d1b64feb34e01f48708d94f8f841a7c9d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550871"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>Arbeiten mit Interop-Ausnahmen in nicht verwaltetem Code

Die Interoperabilität von Ausnahmen wegen nicht verwaltetem Code wird nur auf Windows-Plattformen unterstützt. Auf anderen Plattformen treten Portabilitätsprobleme auf. Da die UNIX-ABI über keine Definition zur Behandlung von Ausnahmen verfügt, kann verwalteter Code nicht erkennen, wie Ausnahmemechanismen im Hintergrund funktionieren. Daher können Ausnahmen zu unvorhersehbarem Verhalten und Abstürzen führen.

## <a name="setjmplongjmp-behaviors"></a>Setjmp/Longjmp-Verhalten

Die Interoperabilität mit den C-Funktionen `setjmp` und `longjmp` wird nicht unterstützt. Sie können `longjmp` nicht zum Überspringen von verwalteten Frames verwenden.

Weitere Informationen finden Sie in der [longjmp-Dokumentation](/cpp/c-runtime-library/reference/longjmp).

## <a name="see-also"></a>Siehe auch

- [Ausnahmen](index.md)
- [Interoperabilität mit nativen Bibliotheken](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
