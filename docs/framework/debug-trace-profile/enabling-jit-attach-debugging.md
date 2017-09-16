---
title: Aktivieren von JIT-attach Debugging
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
caps.latest.revision: 17
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5ca6d1e6ec5c19f690ab862b13783b9db05ac2a9
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="enabling-jit-attach-debugging"></a>Aktivieren von JIT-attach Debugging
Mit „JIT-attach Debugging“ wird das Anfügen eines Debuggers an einen Prozess beim Auftreten von Fehlern beschrieben. Es kann auch von bestimmten Methoden oder Funktionen ausgelöst werden.  
  
 JIT-attach Debugging wird bei den folgenden Fehlerzuständen verwendet:  
  
-   bei Ausnahmefehlern (im nativen und im verwalteten Code)  
  
-   bei der <xref:System.Environment.FailFast%2A?displayProperty=fullName>-Methode oder [RaiseFailFastException](http://go.microsoft.com/fwlink/?LinkId=182107)-Funktion (Windows 7-Produktfamilie)  
  
-   bei schwerwiegenden Laufzeitfehlern  
  
 JIT-attach Debugging wird auch durch Aufrufen der folgenden Methoden und Funktionen ausgelöst:  
  
-   <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=fullName>-Methode.  
  
-   <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=fullName>-Methode.  
  
-   [DebugBreak](http://go.microsoft.com/fwlink/?LinkId=182106)-Funktion (Win32)  
  
 Vor [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] stellte .NET Framework separate Registrierungsschlüssel zur Verhaltenssteuerung von nativen und verwalteten Debuggern bereit. Ab [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] ist die Steuerung unter einem einzelnen Registrierungsschlüssel konsolidiert: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug. Mit den Werten, die Sie für diesen Schlüssel festlegen können, bestimmen Sie, ob ein Debugger aufgerufen wird. Außerdem können Sie festlegen, ob in diesem Fall ein Dialogfeld angezeigt werden soll, das eine Benutzereingabe erfordert. Informationen zum Festlegen dieses Registrierungsschlüssels finden Sie in der MSDN Library unter [Configuring Automatic Debugging (Konfigurieren des automatischen Debuggens)](http://go.microsoft.com/fwlink/?LinkId=181767).  
  
## <a name="see-also"></a>Siehe auch  
 [Debugging, Tracing, and Profiling (Debuggen, Ablaufverfolgung und Profilerstellung)](../../../docs/framework/debug-trace-profile/index.md)   
 [Making an Image Easier to Debug (Erleichtern des Debuggens eines Images)](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)   
 [Aktivieren der Profilerstellung](http://msdn.microsoft.com/en-us/3b669676-f0e0-4ebf-8674-68986dd2020d)

