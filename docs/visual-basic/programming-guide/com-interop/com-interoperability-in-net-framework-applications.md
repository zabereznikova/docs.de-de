---
title: "COM Interoperability in .NET Framework Applications (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interoperability, COM and .NET framework objects"
  - "COM interop"
  - "shared components"
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# COM Interoperability in .NET Framework Applications (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Wenn Sie COM\-Objekte und .NET Framework\-Objekte in derselben Anwendung verwenden möchten, müssen Sie berücksichtigen, dass die Objekte im Speicher in unterschiedlicher Form vorliegen.  Ein .NET Framework\-Objekt befindet sich im verwalteten Arbeitsspeicher, der durch die Common Language Runtime gesteuert wird, und kann von dieser je nach Bedarf verschoben werden.  Ein COM\-Objekt befindet sich im nicht verwalteten Speicher und wird in der Regel nicht an eine andere Position im Speicher verschoben.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] und [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] enthalten Tools zum Steuern der Interaktion dieser verwalteten und nicht verwalteten Komponenten.  Weitere Informationen über verwalteten Code finden Sie unter [Common Language Runtime](../Topic/Common%20Language%20Runtime%20\(CLR\).md).  
  
 Möglicherweise möchten Sie nicht nur COM\-Objekte in .NET\-Anwendungen verwenden, sondern darüber hinaus mit [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] Objekte entwickeln, auf die nicht verwalteter Code über COM zugreifen kann.  
  
 Über die Links auf dieser Seite erhalten Sie weitere Details zu den Interaktionen zwischen COM\- und .NET Framework\-Objekten.  
  
## Verwandte Abschnitte  
 [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 Enthält Links zu Themen, die die COM\-Interoperabilität in Visual Basic behandeln; hierzu gehören unter anderem COM\-Objekte, ActiveX\-Steuerelemente, Win32\-DLLs, verwaltete Objekte und die Vererbung von COM\-Objekten.  
  
 [COM Interop Wrapper Error](/visual-cpp/misc/com-interop-wrapper-error)  
 Erläutert die Folgen und Optionen, wenn das Projektsystem für eine bestimmte Komponente keinen COM\-Interoperabilitätswrapper erstellen kann.  
  
 [Interoperating with Unmanaged Code](../Topic/Interoperating%20with%20Unmanaged%20Code.md)  
 Beschreibt kurz einige Aspekte des Zusammenwirkens von verwaltetem und nicht verwaltetem Code und enthält Links zum Abrufen weiterer Informationen.  
  
 [COM Wrappers](../Topic/COM%20Wrappers.md)  
 Beschreibt Aufrufwrapper der Common Language Runtime, die verwaltetem Code das Aufrufen von COM\-Methoden ermöglichen, sowie COM Callable Wrapper, die COM\-Clients das Aufrufen von .NET\-Objektmethoden ermöglichen.  
  
 [Advanced COM Interoperability](http://msdn.microsoft.com/de-de/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Enthält Links zu Themen, die die COM\-Interoperabilität in Hinsicht auf Wrapper, Ausnahmen, Vererbung, Threading, Ereignisse, Konvertierungen und Marshalling beschreiben.  
  
 [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)  
 Erläutert das Tool, mit dem Sie Typdefinitionen in einer COM\-Typbibliothek in äquivalente Definitionen einer Common Language Runtime\-Assembly konvertieren können.