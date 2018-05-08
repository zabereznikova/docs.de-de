---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d28d0556a662099e4e5e74b22583fc3c8b4c313f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-vbruntime"></a>-vbruntime
Gibt an, dass der Compiler ohne einen Verweis auf die Visual Basic Runtime Library oder mit einem Verweis auf eine bestimmte Laufzeitbibliothek kompilieren soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Argumente  
 \-  
 Kompilieren Sie ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek.  
  
 \+  
 Kompilieren Sie mit einem Verweis auf die Visual Basic-Laufzeitbibliothek.  
  
 \*  
 Kompilieren Sie ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek und betten Sie Kernfunktionalität aus der Visual Basic-Laufzeitbibliothek in die Assembly ein.  
  
 `path`  
 Kompilieren Sie mit einem Verweis auf die angegebene Bibliothek (DLL).  
  
## <a name="remarks"></a>Hinweise  
 Die `-vbruntime` (Compileroption) können Sie angeben, dass der Compiler ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren soll. Wenn Sie ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren, werden Fehler oder Warnungen auf Code oder Sprache Konstrukten protokolliert, die einen Aufruf an eine Visual Basic-Laufzeit-Hilfsprogramm zu generieren. (Ein *Visual Basic-Laufzeit-Hilfsprogramm* ist eine Funktion, die in "Microsoft.VisualBasic.dll", die zur Laufzeit zum Ausführen einer bestimmten Sprache semantische aufgerufen wird.)  
  
 Die `-vbruntime+` Option führt zum gleichen Verhalten, das auftritt, wenn kein `-vbruntime` -Schalter angegeben ist. Können Sie die `-vbruntime+` Option aus, um die vorherigen überschreiben `-vbruntime` Switches.  
  
 Die meisten Objekte von der `My` Typ sind nicht verfügbar, wenn Sie verwenden die `-vbruntime-` oder `-vbruntime:path` Optionen.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Einbetten von Visual Basic-Laufzeit-Kernfunktionalität  
 Die `-vbruntime*` Option ermöglicht es Ihnen, ohne einen Verweis auf eine Laufzeitbibliothek kompiliert werden. Stattdessen ist Kernfunktionalität aus der Visual Basic-Laufzeitbibliothek in der Benutzerassembly eingebettet. Sie können diese Option verwenden, wenn Ihre Anwendung auf Plattformen ausgeführt wird, die der Visual Basic-Laufzeit nicht enthalten.  
  
 Die folgenden Elemente für die Common Language Runtime eingebettet werden:  
  
-   <xref:Microsoft.VisualBasic.CompilerServices.Conversions>-Klasse  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>-Methode  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>-Methode  
  
-   <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>-Methode  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack> Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr> Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf> Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed> Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf> Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine> Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar> Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString> Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab> Konstante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab> Konstante  
  
-   Einige Objekte von der `My` Typ  
  
 Wenn Sie mit: Kompilieren Sie die `-vbruntime*` Option und dem Code verweist auf ein Element aus der Visual Basic-Laufzeitbibliothek, die nicht mit der Kernfunktionalität eingebettet ist, gibt der Compiler einen Fehler, der angibt, dass der Member nicht verfügbar ist.  
  
## <a name="referencing-a-specified-library"></a>Verweis auf eine angegebene Bibliothek  
 Sie können die `path` Argument mit einem Verweis auf eine benutzerdefinierte Laufzeitbibliothek anstelle des standardmäßigen Visual Basic-Laufzeitbibliothek kompiliert.  
  
 Wenn der Wert für die `path` -Argument einen vollqualifizierten Pfad zu einer DLL ist, verwendet der Compiler diese Datei als der Common Language Runtime-Bibliothek. Wenn der Wert für die `path` -Argument keinen vollqualifizierten Pfad zu einer DLL, Visual Basic-Compiler sucht zuerst nach der angegebenen DLL im aktuellen Ordner. Sucht dann in den Pfad, die Sie angegeben haben die [- Sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) -Compileroption. Wenn die `-sdkpath` -Compileroption nicht verwendet wird, sucht des Compilers nach der angegebenen DLL im .NET Framework-Ordner (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die `-vbruntime` Option aus, um mit einem Verweis auf eine benutzerdefinierte Bibliothek zu kompilieren.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic Core – neue Kompilierungsmodus in Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
