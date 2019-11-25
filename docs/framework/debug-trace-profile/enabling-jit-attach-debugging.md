---
title: Aktivieren von JIT-attach Debugging
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be619f8e84b176872361fdd43faa9c704832c8e0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975591"
---
# <a name="enabling-jit-attach-debugging"></a>Aktivieren von JIT-attach Debugging
Mit „JIT-attach Debugging“ wird das Anfügen eines Debuggers an einen Prozess beim Auftreten von Fehlern beschrieben. Es kann auch von bestimmten Methoden oder Funktionen ausgelöst werden.  
  
 JIT-attach Debugging wird bei den folgenden Fehlerzuständen verwendet:  
  
- bei Ausnahmefehlern (im nativen und im verwalteten Code)  
  
- bei der <xref:System.Environment.FailFast%2A?displayProperty=nameWithType>-Methode oder [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception)-Funktion (Windows 7-Produktfamilie)  
  
- bei schwerwiegenden Laufzeitfehlern  
  
 JIT-attach Debugging wird auch durch Aufrufen der folgenden Methoden und Funktionen ausgelöst:  
  
- <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> -Methode.  
  
- <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> -Methode.  
  
- [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak)-Funktion (Win32)  
  
 Vor der .NET Framework 4 haben die .NET Framework separate Registrierungsschlüssel bereitgestellt, um das Verhalten von nativen und verwalteten Debuggern zu steuern. Ab .NET Framework 4 wird die Steuerung unter einem einzelnen Registrierungsschlüssel konsolidiert: HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. Mit den Werten, die Sie für diesen Schlüssel festlegen können, bestimmen Sie, ob ein Debugger aufgerufen wird. Außerdem können Sie festlegen, ob in diesem Fall ein Dialogfeld angezeigt werden soll, das eine Benutzereingabe erfordert. Weitere Informationen zum Festlegen dieses Registrierungsschlüssels finden Sie unter [Konfigurieren des automatischen Debuggens](/windows/win32/debug/configuring-automatic-debugging).  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen, Ablaufverfolgung und Profilerstellung](index.md)
- [Erleichtern des Debuggens für ein Abbild](making-an-image-easier-to-debug.md)
