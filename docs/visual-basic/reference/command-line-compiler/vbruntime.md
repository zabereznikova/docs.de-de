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
ms.openlocfilehash: 8c7789c6af7b82ecb40ecd73d09f64aa1da3fd4b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005054"
---
# <a name="-vbruntime"></a>-vbruntime
Gibt an, dass der Compiler ohne einen Verweis auf die Visual Basic Runtime Library oder mit einem Verweis auf eine bestimmte Laufzeitbibliothek kompilieren soll.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Argumente  
 \-  
 Kompilieren Sie ohne einen Verweis auf die Visual Basic Lauf Zeit Bibliothek.  
  
 \+  
 Kompilieren Sie mit einem Verweis auf die standardmäßige Visual Basic Lauf Zeit Bibliothek.  
  
 \*  
 Kompilieren Sie ohne einen Verweis auf die Visual Basic Lauf Zeit Bibliothek, und Betten Sie die Kernfunktionalität aus der Visual Basic Lauf Zeit Bibliothek in die Assembly ein.  
  
 `path`  
 Kompilieren Sie mit einem Verweis auf die angegebene Bibliothek (dll).  
  
## <a name="remarks"></a>Hinweise  
 Mit der `-vbruntime`-Compileroption können Sie angeben, dass der Compiler ohne einen Verweis auf die Visual Basic Lauf Zeit Bibliothek kompilieren soll. Wenn Sie ohne einen Verweis auf die Visual Basic Lauf Zeit Bibliothek kompilieren, werden Fehler oder Warnungen für Code oder Sprachkonstrukte protokolliert, die einen Visual Basic Runtime-Hilfsobjekt generieren. (Eine *Visual Basic Runtime* -Hilfsprogramm ist eine in "Microsoft. VisualBasic. dll" definierte Funktion, die zur Laufzeit aufgerufen wird, um eine bestimmte sprach Semantik auszuführen.)  
  
 Die Option "`-vbruntime+`" führt zu dem Verhalten, das auftritt, wenn kein `-vbruntime`-Schalter angegeben wird. Sie können die Option "`-vbruntime+`" verwenden, um vorherige `-vbruntime`-Switches zu überschreiben.  
  
 Die meisten Objekte des Typs `My` sind nicht verfügbar, wenn Sie die Optionen `-vbruntime-` oder `-vbruntime:path` verwenden.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Einbettungs Visual Basic Lauf Zeit Kernfunktionalität  
 Die Option "`-vbruntime*`" ermöglicht die Kompilierung ohne Verweis auf eine Lauf Zeit Bibliothek. Stattdessen wird die Kernfunktionalität aus der Visual Basic-Lauf Zeit Bibliothek in die Benutzerassembly eingebettet. Sie können diese Option verwenden, wenn die Anwendung auf Plattformen ausgeführt wird, die die Visual Basic Runtime nicht enthalten.  
  
 Die folgenden Lauf Zeit Elemente sind eingebettet:  
  
- <xref:Microsoft.VisualBasic.CompilerServices.Conversions>-Klasse  
  
- <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>-Methode  
  
- <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>-Methode  
  
- <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>-Methode  
  
- <xref:Microsoft.VisualBasic.Constants.vbBack>-Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbCr>-Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbCrLf>-Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbFormFeed>-Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbLf>-Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbNewLine>-Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbNullChar>-Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbNullString>-Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbTab>-Konstante  
  
- <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>-Konstante  
  
- Einige Objekte des Typs "`My`"  
  
 Wenn Sie mithilfe der Option "`-vbruntime*`" kompilieren und Ihr Code auf ein Element in der Visual Basic-Lauf Zeit Bibliothek verweist, das nicht mit der Kernfunktionalität eingebettet ist, gibt der Compiler einen Fehler zurück, der anzeigt, dass der Member nicht verfügbar ist.  
  
## <a name="referencing-a-specified-library"></a>Verweisen auf eine angegebene Bibliothek  
 Sie können das Argument "`path`" verwenden, um anstelle der standardmäßigen Visual Basic Lauf Zeit Bibliothek mit einem Verweis auf eine benutzerdefinierte Lauf Zeit Bibliothek zu kompilieren.  
  
 Wenn der Wert für das `path`-Argument ein voll qualifizierter Pfad zu einer dll ist, verwendet der Compiler diese Datei als Lauf Zeit Bibliothek. Wenn der Wert für das `path`-Argument kein voll qualifizierter Pfad zu einer dll ist, sucht der Visual Basic Compiler zuerst nach der identifizierten dll im aktuellen Ordner. Anschließend wird in dem Pfad gesucht, den Sie mithilfe der [-sdkpath-](../../../visual-basic/reference/command-line-compiler/sdkpath.md) Compileroption angegeben haben. Wenn die `-sdkpath`-Compileroption nicht verwendet wird, sucht der Compiler nach der identifizierten dll im Ordner .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die Option "`-vbruntime`" zum Kompilieren mit einem Verweis auf eine benutzerdefinierte Bibliothek verwendet wird.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic Core – neuer Kompilierungs Modus in Visual Studio 2010 SP1](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
