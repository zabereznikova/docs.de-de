---
title: Aktivieren von JIT-attach Debugging
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 005395beabd956767b59e0cebd563fe883f6fe53
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489801"
---
# <a name="enabling-jit-attach-debugging"></a>Aktivieren von JIT-attach Debugging
Mit „JIT-attach Debugging“ wird das Anfügen eines Debuggers an einen Prozess beim Auftreten von Fehlern beschrieben. Es kann auch von bestimmten Methoden oder Funktionen ausgelöst werden.  
  
 JIT-attach Debugging wird bei den folgenden Fehlerzuständen verwendet:  
  
- bei Ausnahmefehlern (im nativen und im verwalteten Code)  
  
- bei der <xref:System.Environment.FailFast%2A?displayProperty=nameWithType>-Methode oder [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107)-Funktion (Windows 7-Produktfamilie)  
  
- bei schwerwiegenden Laufzeitfehlern  
  
 JIT-attach Debugging wird auch durch Aufrufen der folgenden Methoden und Funktionen ausgelöst:  
  
- <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> -Methode.  
  
- <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> -Methode.  
  
- [DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106)-Funktion (Win32)  
  
 Vor .NET Framework 4 bereitgestellt, die .NET Framework separate Registrierungsschlüssel zur Steuerung des Verhaltens systemeigenen und verwalteten Debuggern bereit. Ab .NET Framework 4, wird die Steuerung unter einem einzelnen Registrierungsschlüssel konsolidiert: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. Mit den Werten, die Sie für diesen Schlüssel festlegen können, bestimmen Sie, ob ein Debugger aufgerufen wird. Außerdem können Sie festlegen, ob in diesem Fall ein Dialogfeld angezeigt werden soll, das eine Benutzereingabe erfordert. Informationen zum Festlegen dieses Registrierungsschlüssels finden Sie unter [Konfigurieren des automatischen Debuggens](https://go.microsoft.com/fwlink/?LinkId=181767).  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen, Ablaufverfolgung und Profilerstellung](../../../docs/framework/debug-trace-profile/index.md)
- [Erleichtern des Debuggens für ein Abbild](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)
