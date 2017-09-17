---
title: Kompilieren eines Interop-Projekts
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
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a9851366aeb485f056f801251a488d6e8399bf5a
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="compiling-an-interop-project"></a>Kompilieren eines Interop-Projekts
COM-Interop-Projekte, die auf eine oder mehrere Assemblys mit importierten COM-Typen verweisen, werden wie jedes andere verwaltete Projekt kompiliert. Sie können auf Interop-Assemblys in einer Entwicklungsumgebung wie Visual Studio verweisen, oder Sie können darauf verweisen, wenn Sie einen Befehlszeilencompiler verwenden. In beiden Fällen muss die Interop-Assembly zur ordnungsgemäßen Kompilierung im selben Verzeichnis wie die anderen Projektdateien sein.  
  
 Es gibt zwei Möglichkeiten zur Verweisung auf Interop-Assemblys:  
  
-   Eingebettete Interop-Typen: Beginnend mit der [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] und [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] können Sie den Compiler anweisen, die Typinformationen aus einer Interop-Assembly in der ausführbaren Datei einzubetten. Dies ist das empfohlene Verfahren.  
  
-   Durch die Bereitstellung von Interop-Assemblys können Sie einen Standardverweis auf eine Interop-Assembly erstellen. In diesem Fall muss die Interop-Assembly mit Ihrer Anwendung bereitgestellt werden.  
  
 Die Unterschiede zwischen diesen beiden Verfahren werden ausführlich in [Verwenden von COM-Typen in verwaltetem Code](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66) erläutert.  
  
 Das Einbetten von Interop-Typen mit Visual Studio wird in [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3) und [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21) veranschaulicht.  
  
 Verwenden Sie zum Verweisen auf eine Interop-Assembly mit einem Befehlszeilencompiler und Einbetten von Typinformationen in Ihre ausführbaren Dateien die Compilerschalter [/Link (C#-Compileroptionen)](~/docs/csharp/language-reference/compiler-options/link-compiler-option.md) oder [/Link (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/link.md), und geben Sie den Namen der Interop-Assembly an.  
  
> [!NOTE]
>  Visual C++-Anwendungen können keine Typinformationen einbetten, aber sie können mit Anwendungen oder Add-Ins zusammenarbeiten, die dies können.  
  
 Verwenden Sie zum Kompilieren einer Anwendung, die bei der Bereitstellung eine primäre Interop-Assembly enthält, einen **/Referenz**-Compilerschalter, und geben Sie den Namen der Interop-Assembly an.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfügbarmachen von COM-Komponenten für .NET Framework](../../../docs/framework/interop/exposing-com-components.md)   
 [Sprachunabhängigkeit und sprachunabhängige Komponenten](../../../docs/standard/language-independence-and-language-independent-components.md)   
 [Verwenden von COM-Typen in verwaltetem Code](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys](http://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3)   
 [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)   
 [Importieren einer Typbibliothek als Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)

