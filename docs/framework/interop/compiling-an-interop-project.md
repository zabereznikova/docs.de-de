---
title: Kompilieren eines Interop-Projekts
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a1e6ea8a7a7e6869ca9bc6c1b635f30574ac97f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695191"
---
# <a name="compiling-an-interop-project"></a>Kompilieren eines Interop-Projekts

COM-Interop-Projekte, die auf eine oder mehrere Assemblys mit importierten COM-Typen verweisen, werden wie jedes andere verwaltete Projekt kompiliert. Sie können auf Interop-Assemblys in einer Entwicklungsumgebung wie Visual Studio verweisen, oder Sie können darauf verweisen, wenn Sie einen Befehlszeilencompiler verwenden. In beiden Fällen muss die Interop-Assembly zur ordnungsgemäßen Kompilierung im selben Verzeichnis wie die anderen Projektdateien sein.

 Es gibt zwei Möglichkeiten zur Verweisung auf Interop-Assemblys:

-   Eingebettete Interoptypen: Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] und Visual Studio 2010 können Sie den Compiler anweisen, die Typinformationen aus einer Interopassembly in die ausführbare Datei einzubetten. Dies ist das empfohlene Verfahren.

-   Bereitstellen von Interopassemblys: Sie können einen Standardverweis auf eine Interopassembly erstellen. In diesem Fall muss die Interop-Assembly mit Ihrer Anwendung bereitgestellt werden.

 Die Unterschiede zwischen diesen beiden Verfahren werden ausführlich in [Verwenden von COM-Typen in verwaltetem Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)) erläutert.

 Wie Interoptypen mit Visual Studio eingebettet werden, sehen Sie unter [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100)) und [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).

 Verwenden Sie zum Verweisen auf eine Interop-Assembly mit einem Befehlszeilencompiler und Einbetten von Typinformationen in Ihre ausführbaren Dateien die Compilerschalter [/Link (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/link-compiler-option.md) oder [/Link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md), und geben Sie den Namen der Interop-Assembly an.

> [!NOTE]
> Visual C++-Anwendungen können keine Typinformationen einbetten, aber sie können mit Anwendungen oder Add-Ins zusammenarbeiten, die dies können.

 Verwenden Sie zum Kompilieren einer Anwendung, die bei der Bereitstellung eine primäre Interop-Assembly enthält, einen **/Referenz**-Compilerschalter, und geben Sie den Namen der Interop-Assembly an.

## <a name="see-also"></a>Siehe auch

- [Verfügbarmachen von COM-Komponenten für .NET Framework](exposing-com-components.md)
- [Sprachunabhängigkeit und sprachunabhängige Komponenten](../../standard/language-independence-and-language-independent-components.md)
- [Verwenden von COM-Typen in verwaltetem Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))
- [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys in Visual Studio](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))
- [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)
- [Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)](importing-a-type-library-as-an-assembly.md)