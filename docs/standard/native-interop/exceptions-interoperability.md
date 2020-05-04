---
title: Interoperabilität von Ausnahmen
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 2aff71e97e1be0dbb584f4fe43c322cea86d2480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794621"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>Arbeiten mit Interop-Ausnahmen in nicht verwaltetem Code

Die Interoperabilität von Ausnahmen wegen nicht verwaltetem Code wird nur auf Windows-Plattformen unterstützt. Auf anderen Plattformen treten Portabilitätsprobleme auf. Da die UNIX-ABI über keine Definition zur Behandlung von Ausnahmen verfügt, kann verwalteter Code nicht erkennen, wie Ausnahmemechanismen im Hintergrund funktionieren. Daher können Ausnahmen zu unvorhersehbarem Verhalten und Abstürzen führen.

## <a name="setjmplongjmp-behaviors"></a>Setjmp/Longjmp-Verhalten

Die Interoperabilität mit den C-Funktionen `setjmp` und `longjmp` wird nicht unterstützt. Sie können `longjmp` nicht zum Überspringen von verwalteten Frames verwenden.

Weitere Informationen finden Sie in der [longjmp-Dokumentation](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).

## <a name="see-also"></a>Siehe auch

- [Ausnahmen](index.md)
- [Interoperabilität mit nativen Bibliotheken](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
