---
title: COM-Interoperabilität in .NET Framework-Anwendungen
ms.date: 07/20/2015
helpviewer_keywords:
- interoperability, COM and .NET Framework objects
- COM interop [Visual Basic]
- shared components
ms.assetid: f5a72143-c268-4dff-a019-974ad940e17d
ms.openlocfilehash: c3567464616d3b0b3f91ff57e8a169aca046c866
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452291"
---
# <a name="com-interoperability-in-net-framework-applications-visual-basic"></a>COM-Interoperabilität in .NET Framework-Anwendungen (Visual Basic)

Wenn Sie COM-Objekte und .NET Framework-Objekte in derselben Anwendung verwenden möchten, müssen Sie die Unterschiede in der Art und Weise berücksichtigen, in der die Objekte im Arbeitsspeicher vorhanden sind. Ein .NET Framework-Objekt befindet sich im verwalteten Speicher – der vom Common Language Runtime gesteuerte Arbeitsspeicher – und kann ggf. von der Laufzeit verschoben werden. Ein COM-Objekt befindet sich im nicht verwalteten Speicher und wird nicht erwartet, dass es an einen anderen Speicherort verschoben wird. Visual Studio und die .NET Framework bieten Tools, mit denen Sie die Interaktion dieser verwalteten und nicht verwalteten Komponenten steuern können. Weitere Informationen zu verwaltetem Code finden Sie unter [Common Language Runtime](../../../standard/clr.md).

Zusätzlich zur Verwendung von COM-Objekten in .NET-Anwendungen möchten Sie möglicherweise auch Visual Basic verwenden, um Objekte zu entwickeln, auf die von nicht verwaltetem Code über com zugegriffen werden kann.

Die Links auf dieser Seite bieten Details zu Interaktionen zwischen com-und .NET Framework Objekten.

## <a name="related-sections"></a>Verwandte Abschnitte

| | |
|---------|---------|
| [COM-Interop](../../../visual-basic/programming-guide/com-interop/index.md) | Enthält Links zu Themen, die die COM-Interoperabilität in Visual Basic abdecken, einschließlich COM-Objekte, ActiveX-Steuerelementen, Win32-DLLs, verwalteten Objekten und Vererbung von COM-Objekten. |
| [Interoperabilität mit nicht verwaltetem Code](../../../framework/interop/index.md) | Beschreibt kurz einige Interaktions Probleme zwischen verwaltetem und nicht verwaltetem Code und stellt Links zur weiteren Untersuchung bereit. |
| [COM-Wrapper](../../../standard/native-interop/com-wrappers.md) | Erläutert Runtime Callable Wrapper, die es verwaltetem Code ermöglichen, com-Methoden und COM Callable Wrapper aufzurufen, die com-Clients das Aufrufen von .net-Objektmethoden ermöglichen. |
| [Erweiterte COM-Interoperabilität](../../../framework/interop/index.md) | Enthält Links zu Themen, in denen die COM-Interoperabilität in Bezug auf Wrapper, Ausnahmen, Vererbung, Threading, Ereignisse, Konvertierungen und Marshalling behandelt wird. |
| [Tlbimp.exe (Type Library Importer-Tool)](../../../framework/tools/tlbimp-exe-type-library-importer.md) | Erläutert das Tool, das Sie verwenden können, um die in einer COM-Typbibliothek gefundenen Typdefinitionen in äquivalente Definitionen in einer Common Language Runtime Assembly zu konvertieren. |
