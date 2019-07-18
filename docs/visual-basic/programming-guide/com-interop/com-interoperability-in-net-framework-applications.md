---
title: COM-Interoperabilität in .NET Framework-Anwendungen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: 76c953941d2b8e7af5e4894fd1c521d62e64860f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642123"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>COM-Interoperabilität in .NET Framework-Anwendungen (Visual Basic)

Wenn Sie COM-Objekte und .NET Framework-Objekte in der gleichen Anwendung verwenden möchten, müssen Sie behandeln die Unterschiede wie die Objekte im Arbeitsspeicher vorhanden. .NET Framework-Objekt befindet sich im verwalteten Speicher, der Arbeitsspeicher, die von der common Language Runtime gesteuert, von der Runtime verschoben werden kann, je nach Bedarf. Ein COM-Objekt befindet sich im nicht verwalteten Speicher und nicht an einen anderen Speicherort verschieben soll. Stellen Tools zum Steuern der Interaktion dieser verwalteten und nicht verwalteten Komponenten, Visual Studio und .NET Framework. Weitere Informationen zu verwaltetem Code finden Sie unter [Common Language Runtime](../../../standard/clr.md).

Zusätzlich zur Verwendung von COM-Objekte in .NET-Anwendungen, sollten Sie auch Visual Basic verwenden, zum Entwickeln von Objekten aus nicht verwaltetem Code über COM zugegriffen werden kann

Die Links auf dieser Seite die Details auf die Interaktionen zwischen COM und .NET Framework-Objekte.

## <a name="related-sections"></a>Verwandte Abschnitte

| | |
|---------|---------|
| [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md) | Enthält Links zu Themen, in denen COM-Interoperabilität in Visual Basic, einschließlich COM-Objekten, ActiveX-Steuerelemente, Win32-DLLs, verwaltete Objekte und Vererbung von COM-Objekten. |
| [Interoperabilität mit nicht verwaltetem Code](../../../framework/interop/index.md) | Kurz einige der Probleme Interaktion zwischen verwaltetem und nicht verwaltetem Code beschrieben, und enthält Links für weitere Studien. |
| [COM-Wrapper](../../../framework/interop/com-wrappers.md) | Erläutert, Runtime callable Wrapper, die verwalteten Code zum Aufrufen von COM-Methoden zu ermöglichen, und COM callable Wrapper, die COM-Clients .NET Objekt-Methoden aufrufen können. |
| [Erweiterte COM-Interoperabilität](../../../framework/interop/index.md) | Enthält Links zu Themen, in denen COM-Interoperabilität in Bezug auf Wrapper, Ausnahmen, Vererbung, threading, Ereignisse, Konvertierungen und Marshalling. |
| [Tlbimp.exe (Type Library Importer-Tool)](../../../framework/tools/tlbimp-exe-type-library-importer.md) | Beschreibt die Tools, die Sie verwenden können, um die Typdefinitionen in einer COM-Typbibliothek in äquivalente Definitionen einer common Language Runtime-Assembly zu konvertieren. |
