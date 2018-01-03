---
title: "COM-Interoperabilität in .NET Framework-Anwendungen (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0c84143e22f33f572447c50e33559a52469b181a
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>COM-Interoperabilität in .NET Framework-Anwendungen (Visual Basic)
Wenn Sie COM-Objekte und .NET Framework-Objekte in derselben Anwendung verwenden möchten, müssen Sie behandeln die Unterschiede in wie die Objekte im Arbeitsspeicher vorhanden. .NET Framework-Objekt befindet sich im verwalteten Speicher – der Arbeitsspeicher, die von der common Language Runtime gesteuert – und von der Runtime verschoben werden kann, je nach Bedarf. Ein COM-Objekt befindet sich im nicht verwalteten Speicher und ist nicht dazu gedacht, die an einen anderen Speicherort verschieben. [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] bieten Tools steuern Sie die Interaktion dieser verwalteten und nicht verwalteten Komponenten. Weitere Informationen zu verwaltetem Code finden Sie unter [Common Language Runtime](../../../standard/clr.md).  
  
 Zusätzlich zur Verwendung von COM-Objekten in .NET-Anwendungen können Sie möglicherweise auch verwenden möchten [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] zum Entwickeln von Objekten aus nicht verwaltetem Code durch COM zugegriffen werden kann  
  
 Die Links auf dieser Seite enthalten Details zu den Interaktionen zwischen COM- und .NET Framework-Objekten.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 Enthält Links zu Themen über COM-Interoperabilität in Visual Basic, z. B. com-Objekte, ActiveX-Steuerelemente, Win32-DLLs, verwaltete Objekte und Vererbung von COM-Objekten.  
  
 [COM-Interop-Wrapperfehler](/cpp/misc/com-interop-wrapper-error)  
 Beschreibt die folgen und Optionen an, wenn das Projektsystem einen COM-Interoperabilität-Wrapper für eine bestimmte Komponente erstellt werden kann.  
  
 [Interoperabilität mit nicht verwaltetem Code](../../../framework/interop/index.md)  
 Beschreibt kurz einige der Probleme Interaktion zwischen verwaltetem und nicht verwaltetem Code, und enthält Links zur weiteren Überprüfung kennzeichnen.  
  
 [COM-Wrapper](../../../framework/interop/com-wrappers.md)  
 Erläutert, Runtime callable Wrapper, kann verwalteten Code COM-Methoden aufrufen und COM callable Wrapper, die COM-Clients zum Aufrufen von Objektmethoden .NET zu ermöglichen.  
  
 [Erweiterte COM-Interoperabilität](../../../framework/interop/index.md)  
 Enthält Links zu Themen über COM-Interoperabilität in Bezug auf den Wrapper, Ausnahmen, Vererbung, threading, Ereignisse, Konvertierungen und Marshallen.  
  
 [Tlbimp.exe (Type Library Importer-Tool)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 Erläutert das Tool, das Sie verwenden können, um die Typdefinitionen in einer COM-Typbibliothek in äquivalente Definitionen einer common Language Runtime-Assembly zu konvertieren.
