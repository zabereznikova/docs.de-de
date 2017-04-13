---
title: "Compiling an Interop Project | Microsoft Docs"
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
  - "interoperation with unmanaged code, compiling"
  - "COM interop, compiling"
  - "exposing COM components to .NET Framework"
  - "compiling interop projects"
  - "interoperation with unmanaged code, exposing COM components"
  - "COM interop, exposing COM components"
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Compiling an Interop Project
COM\-Interop\-Projekte, die Assemblys mit einem oder mehreren importierten COM\-Typen verweisen, werden in gleicher Weise kompiliert wie alle anderen verwalteten Projekte.  Sie können Interopassemblys in einer Entwicklungsumgebung wie z. B. Visual Studio, mit Verweisen versehen, oder Sie können sie mit Verweisen versehen, wenn Sie einen Befehlszeilencompiler verwenden.  In jedem Fall muss sich die Interopassembly im selben Verzeichnis wie die anderen Projektdateien befinden, damit die Kompilierung ordnungsgemäß abläuft.  
  
 Es gibt zwei Möglichkeiten, auf Interopassemblys zu verweisen:  
  
-   Eingebettete Interop\-Typen: Wenn Sie mit [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] und [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] beginnen, können Sie den Compiler anweisen, Typinformationen von einer Interopassembly in die EXE\-Datei einzubetten.  Dies ist das empfohlene Verfahren.  
  
-   Bereitstellen von Interopassemblys: Sie können einen Standardverweis auf eine Interopassembly erstellen.  In diesem Fall muss die Interopassembly mit der Anwendung bereitgestellt werden.  
  
 Die Unterschiede zwischen diesen zwei Methoden werden ausführlich in [Using COM Types in Managed Code](http://msdn.microsoft.com/de-de/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66) erläutert.  
  
 Die Einbettung von Interop\-Typen mit Visual Studio wird in [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office\-Assemblys](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md) und [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md) veranschaulicht.  
  
 Um mit einem Befehlszeilencompiler auf eine Interopassembly zu verweisen und Typinformationen in die ausführbaren Dateien einzubetten, verwenden Sie den [\/link \(Link to COM Assembly\)](../Topic/-link%20\(C%23%20Compiler%20Options\).md)\-Compilerschalter oder den [\/link](../Topic/-link%20\(Visual%20Basic\).md)\-Compilerschalter, und geben Sie den Namen der Interopassembly an.  
  
> [!NOTE]
>  Visual C\+\+\-Anwendungen können keine Typinformationen einbetten, doch sie können mit Anwendungen oder Add\-Ins zusammenwirken, die diese Möglichkeit besitzen.  
  
 Zum Kompilieren einer Anwendung, die eine primäre Interopassembly einschließt, wenn sie bereitgestellt wird, verwenden Sie den **\/reference**\-Compilerschalter, und geben Sie den Namen der Interopassembly an.  
  
## Siehe auch  
 [Exposing COM Components to the .NET Framework](../../../docs/framework/interop/exposing-com-components.md)   
 [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../docs/standard/language-independence-and-language-independent-components.md)   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/de-de/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office\-Assemblys](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)