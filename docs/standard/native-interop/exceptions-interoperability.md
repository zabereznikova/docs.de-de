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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794621"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>Arbeiten mit Interop-Ausnahmen in nicht verwaltetem Code

Ausnahme-Interop von nicht verwaltetem Code wird nur auf Windows-Plattformen unterstützt. Portabilitäts Probleme treten auf nicht-Windows-Plattformen auf. Da die UNIX-ABI nicht über eine Definition zur Ausnahmebehandlung verfügt, kann verwalteter Code nicht erkennen, wie Ausnahme Mechanismen unter den Decken funktionieren. Daher können Ausnahmen zu unvorhersehbaren Verhalten und Abstürzen führen.

## <a name="setjmplongjmp-behaviors"></a>Setjmp/longjmp-Verhalten

Interop mit `setjmp`-und `longjmp` C-Funktionen wird nicht unterstützt. Sie können `longjmp` nicht verwenden, um verwaltete Frames zu überspringen.

Weitere Informationen finden Sie in der [longjmp-Dokumentation](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).

## <a name="see-also"></a>Siehe auch

- [Ausnahmen](index.md)
- [Interop mit nativen Bibliotheken](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
