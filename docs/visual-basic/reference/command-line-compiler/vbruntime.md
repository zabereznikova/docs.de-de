---
title: "/vbruntime | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbruntime"
  - "/vbruntime"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "vbruntime compiler option [Visual Basic]"
  - "-vbruntime compiler option [Visual Basic]"
  - "/vbruntime compiler option [Visual Basic]"
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /vbruntime
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt an, dass der Compiler ohne einen Verweis auf die Visual Basic Runtime Library oder mit einem Verweis auf eine bestimmte Laufzeitbibliothek kompilieren soll.  
  
## Syntax  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## Argumente  
 \-  
 Ohne Verweis auf die Visual Basic Runtime Library kompilieren.  
  
 \+  
 Mit Verweis auf die Standard\-Visual Basic Runtime Library kompilieren.  
  
 \*  
 Kompilieren Sie ohne einen Verweis auf die Visual Basic\-Laufzeitbibliothek und betten Sie die Kernfunktionalität aus der Visual Basic\-Laufzeitbibliothek in die Assembly ein.  
  
 `path`  
 Mit einem Verweis auf die angegebene Bibliothek \(DLL\) kompilieren.  
  
## Hinweise  
 Die `/vbruntime`\-Compileroption ermöglicht das Festlegen, dass der Compiler ohne Verweis auf die Visual Basic Runtime Library kompilieren soll.  Wenn Sie ohne Verweis auf die Visual Basic Runtime Library kompilieren, werden für Code\- oder Sprachkonstrukte, die einen Aufruf einer Visual Basic\-Laufzeithilfsfunktion durchführen, Fehler oder Warnungen protokolliert.  \(Eine *Visual Basic\-Laufzeithilfsfunktion* ist eine Funktion, die in Microsoft.VisualBasic.dll definiert ist und zur Laufzeit aufgerufen wird, um eine bestimmte Sprachsemantik auszuführen.\)  
  
 Die `/vbruntime+`\-Option führt zum selben Verhalten wie beim Nichtangeben des `/vbruntime`\-Schalters.  Sie können die `/vbruntime+`\-Option verwenden, um vorherige `/vbruntime`\-Schalter zu überschreiben.  
  
 Die meisten Objekte des `My` Typs sind nicht verfügbar, wenn Sie die `/vbruntime-` oder Optionen `vbruntime:``path` verwenden.  
  
## Einbetten von Visual Basic\-Laufzeit\-Kernfunktionalität  
 Die `/vbruntime*` \-Option können Sie ohne einen Verweis auf eine Laufzeitbibliothek kompilieren.  Stattdessen ist Kernfunktionalität der der Visual Basic\-Laufzeitbibliothek in der Benutzerassembly eingebettet.  Sie können diese Option verwenden, wenn die Anwendung auf Plattformen ausgeführt wird, die keine die Visual Basic\-Laufzeit enthalten.  
  
 Die folgenden Laufzeit\-Member sind eingebettet:  
  
-   <xref:Microsoft.VisualBasic.CompilerServices.Conversions>\-Klasse  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>\-Methode  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>\-Methode  
  
-   <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>\-Methode  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack>\-Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr>\-Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf>\-Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed>\-Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf>\-Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine>\-Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar>\-Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString>\-Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab>\-Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>\-Konstante  
  
-   Einige Objekte des Typs `My`  
  
 Wenn Sie mit der Option `/vbruntime*` kompilieren und Code auf einen Member aus der Visual Basic\-Laufzeitbibliothek verweist, der nicht in die Kernfunktionen eingebettet ist, gibt der Compiler einen Fehler aus, der angibt, dass der Member nicht verfügbar ist.  
  
## Verweisen auf eine angegebene Bibliothek  
 Sie können das `path`\-Argument verwenden, um mit einem Verweis auf eine benutzerdefinierte Laufzeitbibliothek anstelle der Standard\-Visual Basic Runtime Library zu kompilieren.  
  
 Wenn der Wert für das `path`\-Argument ein vollqualifizierter Pfad zu einer DLL ist, verwendet der Compiler diese Datei als Laufzeitbibliothek.  Wenn der Wert für das `path`\-Argument kein vollqualifizierter Pfad zu einer DLL ist, sucht der Visual Basic\-Compiler zunächst im aktuellen Ordner nach der angegebenen DLL.  Danach sucht der Compiler in dem Pfad, den Sie in der [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)\-Compileroption angegeben haben.  Wenn die `/sdkpath`\-Compileroption nicht verwendet wird, sucht der Compiler nach der angegebenen DLL im .NET Framework\-Ordner \(`%systemroot%\Microsoft.NET\Framework\versionNumber`\).  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die `/vbruntime`\-Option verwendet wird, um mit einem Verweis auf eine benutzerdefinierte Bibliothek zu kompilieren.  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## Siehe auch  
 [Visual Basic Core – Neuer Kompilierungsmodus in Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)   
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)