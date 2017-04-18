---
title: "COM-Interoperabilität in .NET Framework Applications (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 308ee8e495efa9368ef55d781f6b6dc314db51ac
ms.lasthandoff: 03/13/2017

---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>COM-Interoperabilität in .NET Framework-Anwendungen (Visual Basic)
Wenn Sie COM-Objekte und .NET Framework-Objekte in der gleichen Anwendung verwenden möchten, müssen Sie auf die Unterschiede zwischen wie die Objekte im Arbeitsspeicher vorhanden sind. .NET Framework-Objekt befindet sich im verwalteten Speicher – der Arbeitsspeicher, die von der common Language Runtime gesteuert, durch die Common Language Runtime verschoben werden kann, je nach Bedarf. Ein COM-Objekt wird befindet sich im nicht verwalteten Speicher und nicht an einen anderen Speicherort verschieben. [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]und die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] bieten Tools zum Steuern der Interaktion dieser verwalteten und nicht verwalteten Komponenten. Weitere Informationen zu verwaltetem Code finden Sie unter [Common Language Runtime](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).  
  
 Neben der Verwendung von COM-Objekten in .NET-Anwendungen können Sie möglicherweise auch verwenden möchten [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] zum Entwickeln von Objekten aus nicht verwaltetem Code über COM zugegriffen werden kann  
  
 Die Links auf dieser Seite enthalten Details zu den Interaktionen zwischen COM- und .NET Framework-Objekten.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md)  
 Enthält Links zu Themen über COM-Interoperabilität in Visual Basic, darunter COM-Objekte, ActiveX-Steuerelemente, Win32-DLLs, verwaltete Objekte und Vererbung von COM-Objekten.  
  
 [COM-Interop-Wrapperfehler](https://docs.microsoft.com/cpp/misc/com-interop-wrapper-error)  
 Beschreibt die folgen und Optionen, wenn das Projektsystem einen COM-Interoperabilität-Wrapper für eine bestimmte Komponente erstellt werden kann.  
  
 [Interoperation mit nicht verwaltetem Code](https://msdn.microsoft.com/library/sd10k43k)  
 Kurz beschreibt einige der Probleme für die Interaktion zwischen verwaltetem und nicht verwaltetem Code und enthält Links zum Abrufen weiterer Informationen.  
  
 [COM-Wrapper](http://msdn.microsoft.com/library/e56c485b-6b67-4345-8e66-fd21835a6092)  
 Erläutert, Runtime callable Wrapper, die verwalteten Code zum Aufrufen von COM-Methoden ermöglichen, sowie COM callable Wrapper, die COM-Clients Aufrufen von.  
  
 [Erweiterte COM-Interoperabilität](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Enthält Links zu Themen über COM-Interoperabilität in Bezug auf den Wrapper, Ausnahmen, Vererbung, threading, Ereignisse, Konvertierungen und Marshalling.  
  
 [Tlbimp.exe (Type Library Importer-Tool)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)  
 Beschreibt das Tool, das Sie verwenden können, konvertiert die Typdefinitionen in einer COM-Typbibliothek in äquivalente Definitionen einer common Language Runtime-Assembly.
