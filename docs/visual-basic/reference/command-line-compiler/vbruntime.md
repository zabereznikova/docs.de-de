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
ms.openlocfilehash: 56ea692d6e65d94c497fbc9406e03b40648c55a2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663495"
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
 Ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren und Kernfunktionen, die aus der Visual Basic-Laufzeitbibliothek in die Assembly einbetten.  
  
 `path`  
 Kompilieren Sie mit einem Verweis auf die angegebene Bibliothek (DLL).  
  
## <a name="remarks"></a>Hinweise  
 Die `-vbruntime` Compileroption können Sie angeben, dass der Compiler ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren soll. Wenn Sie ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren, werden Fehler oder Warnungen auf Code oder Sprache Konstrukten protokolliert, die einen Aufruf einer Visual Basic-Laufzeit-Hilfsprogramm zu generieren. (Ein *Visual Basic-Laufzeit-Hilfsprogramm* ist eine Funktion definiert, die in "Microsoft.VisualBasic.dll", die zur Laufzeit zum Ausführen einer bestimmten Sprache semantische aufgerufen wird.)  
  
 Die `-vbruntime+` Option erzeugt das gleiche Verhalten, wenn kein `-vbruntime` -Schalter angegeben ist. Sie können die `-vbruntime+` Option zum Überschreiben der vorherigen `-vbruntime` Switches.  
  
 Die meisten Objekte von der `My` Typ sind nicht verfügbar, wenn Sie verwenden die `-vbruntime-` oder `-vbruntime:path` Optionen.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Einbetten von Visual Basic-Laufzeit-Kernfunktionen  
 Die `-vbruntime*` Option können Sie ohne einen Verweis auf eine Common Language Runtime-Bibliothek zu kompilieren. Stattdessen wird Kernfunktionen aus der Visual Basic-Laufzeitbibliothek in der Benutzerassembly eingebettet. Sie können diese Option verwenden, wenn Ihre Anwendung auf Plattformen ausgeführt wird, die nicht die Visual Basic-Laufzeit enthalten.  
  
 Es werden die folgenden Elemente für die Common Language Runtime eingebettet:  
  
- <xref:Microsoft.VisualBasic.CompilerServices.Conversions>-Klasse  
  
- <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>-Methode  
  
- <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>-Methode  
  
- <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>-Methode  
  
- <xref:Microsoft.VisualBasic.Constants.vbBack> Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbCr> Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbCrLf> Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbFormFeed> Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbLf> Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbNewLine> Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbNullChar> Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbNullString> Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbTab> Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbVerticalTab> Konstante  
  
- Einige Objekte von der `My` Typ  
  
 Wenn Sie mit der Kompilierung der `-vbruntime*` Option und den Code verweist auf ein Element aus der Visual Basic-Laufzeitbibliothek, die nicht mit den wichtigsten Funktionen eingebettet ist, gibt der Compiler einen Fehler, der angibt, dass das Element nicht verfügbar ist.  
  
## <a name="referencing-a-specified-library"></a>Verweisen auf einer angegebenen Bibliothek  
 Sie können die `path` Argument mit einem Verweis auf eine benutzerdefinierte Laufzeitbibliothek anstelle der standardmäßigen Visual Basic-Laufzeitbibliothek kompilieren.  
  
 Wenn der Wert für die `path` Argument ist, einen vollqualifizierten Pfad zu einer DLL, die der Compiler verwendet diese Datei als die Runtime-Bibliothek. Wenn der Wert für die `path` -Argument keinen vollqualifizierten Pfad zu einer DLL, Visual Basic-Compiler wird zuerst nach der angegebenen DLL im aktuellen Ordner gesucht. Danach sucht in den Pfad der von Ihnen mithilfe angegebene der [- Sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) -Compileroption. Wenn die `-sdkpath` Compileroption nicht verwendet wird, sucht der Compiler nach der angegebenen DLL in .NET Framework-Ordner (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie mit der `-vbruntime` Option aus, um mit einem Verweis auf eine benutzerdefinierte Bibliothek zu kompilieren.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Core – neue Kompilierungsmodus in Visual Studio 2010 SP1](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
