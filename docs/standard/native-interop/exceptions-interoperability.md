---
title: Interoperabilität von Ausnahmen
ms.date: 01/16/2020
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: db7c9943c298607aa91a4bd08ddc12bbafc872be
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830622"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>Arbeiten mit Interop-Ausnahmen in nicht verwaltetem Code

Die Interoperabilität von Ausnahmen wegen nicht verwaltetem Code wird nur auf Windows-Plattformen unterstützt. Auf anderen Plattformen treten Portabilitätsprobleme auf. Da die UNIX-ABI über keine Definition zur Behandlung von Ausnahmen verfügt, kann verwalteter Code nicht erkennen, wie Ausnahmemechanismen im Hintergrund funktionieren. Daher können Ausnahmen zu unvorhersehbarem Verhalten und Abstürzen führen.

## <a name="setjmplongjmp-behaviors"></a>Setjmp/Longjmp-Verhalten

Die Interoperabilität mit den C-Funktionen `setjmp` und `longjmp` wird nicht unterstützt. Sie können `longjmp` nicht zum Überspringen von verwalteten Frames verwenden.

Weitere Informationen finden Sie in der [longjmp-Dokumentation](/cpp/c-runtime-library/reference/longjmp).

## <a name="see-also"></a>Siehe auch

- [Ausnahmen](index.md)
- [Interoperabilität mit nativen Bibliotheken](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
