---
title: "Enabling JIT-Attach Debugging | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "JIT-attach debugging"
  - "debugging [.NET Framework], JIT-attach debugging"
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Enabling JIT-Attach Debugging
Mit dem Ausdruck JIT\-attach Debugging wird das Anfügen eines Debuggers an einen Prozess beim Auftreten von Fehlern beschrieben, das Anfügen kann aber auch von bestimmten Methoden oder Funktionen ausgelöst werden.  
  
 JIT\-attach Debugging wird bei den folgenden Fehlerzuständen verwendet:  
  
-   Nicht behandelte Ausnahmen \(in systemeigenem und in verwaltetem Code\).  
  
-   <xref:System.Environment.FailFast%2A?displayProperty=fullName>\-Methode oder [RaiseFailFastException](http://go.microsoft.com/fwlink/?LinkId=182107)\-Funktion \(Windows 7\-Produktfamilie\).  
  
-   Schwerwiegende Laufzeitfehler.  
  
 JIT\-attach Debugging wird auch durch Aufrufe der folgenden Methoden und Funktionen ausgelöst:  
  
-   <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=fullName>\-Methode.  
  
-   <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=fullName>\-Methode.  
  
-   [DebugBreak](http://go.microsoft.com/fwlink/?LinkId=182106)\-Funktion \(Win32\).  
  
 Vor [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] stellt .NET Framework separate Registrierungsschlüssel bereit, um das Verhalten systemeigener und verwalteter Debugger zu steuern.  Ab [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] ist die Steuerung unter einem einzelnen Registrierungsschlüssel konsolidiert: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\Current Version\\AeDebug.  Die Werte, die Sie für diesen Schlüssel festlegen können, bestimmen, ob ein Debugger aufgerufen wird, und ob dieser in diesem Fall mit einem Dialogfeld aufgerufen wird, das ein Eingreifen des Benutzers erfordert.  Informationen zum Festlegen dieses Registrierungsschlüssels, finden Sie unter [Konfigurieren des automatischen Debuggens](http://go.microsoft.com/fwlink/?LinkId=181767) in der MSDN Library.  
  
## Siehe auch  
 [Debugging, Tracing, and Profiling](../../../docs/framework/debug-trace-profile/index.md)   
 [Erleichtern des Debuggens für ein Abbild](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)   
 [Enabling Profiling](http://msdn.microsoft.com/de-de/3b669676-f0e0-4ebf-8674-68986dd2020d)