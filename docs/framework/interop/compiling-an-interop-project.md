---
title: Kompilieren eines Interop-Projekts
description: Erfahren Sie, wie ein COM-Interop-Projekt kompiliert wird, das wie eine verwaltetes Projekt kompiliert wird, wenn es auf eine oder mehrere Assemblys verweist, die importierte COM-Typen enthalten.
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
ms.openlocfilehash: 1cf5bdbedd53227e812b0d2ed97778ab34a81444
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557096"
---
# <a name="compiling-an-interop-project"></a>Kompilieren eines Interop-Projekts

COM-Interop-Projekte, die auf eine oder mehrere Assemblys mit importierten COM-Typen verweisen, werden wie jedes andere verwaltete Projekt kompiliert. Sie können auf Interop-Assemblys in einer Entwicklungsumgebung wie Visual Studio verweisen, oder Sie können darauf verweisen, wenn Sie einen Befehlszeilencompiler verwenden. In beiden Fällen muss die Interop-Assembly zur ordnungsgemäßen Kompilierung im selben Verzeichnis wie die anderen Projektdateien sein.

 Es gibt zwei Möglichkeiten zur Verweisung auf Interop-Assemblys:

- Eingebettete Interoptypen: Ab .NET Framework 4 und Visual Studio 2010 können Sie den Compiler anweisen, die Typinformationen aus einer Interopassembly in die ausführbare Datei einzubetten. Dies ist das empfohlene Verfahren.

- Bereitstellen von Interopassemblys: Sie können einen Standardverweis auf eine Interopassembly erstellen. In diesem Fall muss die Interop-Assembly mit Ihrer Anwendung bereitgestellt werden.

 Die Unterschiede zwischen diesen beiden Verfahren werden ausführlich in [Verwenden von COM-Typen in verwaltetem Code](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)) erläutert.

 Wie Interoptypen mit Visual Studio eingebettet werden, sehen Sie unter [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio](../../standard/assembly/embed-types-visual-studio.md).

 Verwenden Sie zum Verweisen auf eine Interop-Assembly mit einem Befehlszeilencompiler und Einbetten von Typinformationen in Ihre ausführbaren Dateien die Compilerschalter [-Link (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/link-compiler-option.md) oder [-Link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md), und geben Sie den Namen der Interop-Assembly an.

> [!NOTE]
> Visual C++-Anwendungen können keine Typinformationen einbetten, aber sie können mit Anwendungen oder Add-Ins zusammenarbeiten, die dies können.

 Verwenden Sie zum Kompilieren einer Anwendung, die bei der Bereitstellung eine primäre Interop-Assembly enthält, einen **/Referenz**-Compilerschalter, und geben Sie den Namen der Interop-Assembly an.

## <a name="see-also"></a>Siehe auch

- [Verfügbarmachen von COM-Komponenten für .NET Framework](exposing-com-components.md)
- [Sprachunabhängigkeit und sprachunabhängige Komponenten](../../standard/language-independence-and-language-independent-components.md)
- [Verwenden von COM-Typen in verwaltetem Code](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))
- [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio](../../standard/assembly/embed-types-visual-studio.md)
- [Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)](importing-a-type-library-as-an-assembly.md)
