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
ms.openlocfilehash: 46d4b095d4a2bf9aac9124d5d4b2a09adb347ba1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085060"
---
# <a name="-vbruntime"></a>-vbruntime

Gibt an, dass der Compiler ohne einen Verweis auf die Visual Basic Runtime Library oder mit einem Verweis auf eine bestimmte Laufzeitbibliothek kompilieren soll.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Argumente  

 \-  
 Kompilieren Sie ohne einen Verweis auf die Visual Basic-Runtimebibliothek.  
  
 \+  
 Kompilieren Sie mit einem Verweis auf die Visual Basic-Standardruntimebibliothek.  
  
 \*  
 Kompilieren Sie ohne einen Verweis auf die Visual Basic-Runtimebibliothek, und betten Sie die deren Kernfunktionalität in die Assembly ein.  
  
 `path`  
 Kompilieren Sie mit einem Verweis auf die angegebene Bibliothek (DLL).  
  
## <a name="remarks"></a>Hinweise  

 Mit der `-vbruntime`-Compileroption können Sie festlegen, dass der Compiler ohne einen Verweis auf die Visual Basic-Runtimebibliothek kompilieren soll. Wenn Sie ohne einen Verweis auf die Visual Basic-Runtimebibliothek kompilieren, werden Fehler oder Warnungen für Code- oder Sprachkonstrukte protokolliert, die einen Aufruf eines Visual Basic-Runtimehilfsprogramms bewirken. (Ein *Visual Basic-Runtimehilfsprogramm* ist eine in Microsoft.VisualBasic.dll definierte Funktion, die zur Laufzeit aufgerufen wird, um eine bestimmte Sprachsemantik auszuführen.)  
  
 Die Option `-vbruntime+` führt zum selben Verhalten wie bei einem nicht angegebenem `-vbruntime`-Switch. Sie können die Option `-vbruntime+` verwenden, um vorherige `-vbruntime`-Switches zu überschreiben.  
  
 Die meisten Objekte des `My`-Typs sind nicht verfügbar, wenn Sie die Optionen `-vbruntime-` oder `-vbruntime:path` verwenden.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Einbetten der Kernfunktionalität der Visual Basic-Runtimebibliothek  

 Mit der `-vbruntime*`-Option können Sie ohne einen Verweis auf eine Runtimebibliothek kompilieren. Stattdessen wird die Kernfunktionalität der Visual Basic-Runtimebibliothek in die Benutzerassembly eingebettet. Sie können diese Option verwenden, wenn die Anwendung auf Plattformen ausgeführt wird, die die Visual Basic-Runtimebibliothek nicht enthalten.  
  
 Die folgenden Member der Runtimebibliothek sind eingebettet:  
  
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
  
- Objekte des `My`-Typs  
  
 Wenn Sie mithilfe der Option `-vbruntime*` kompilieren und Ihr Code auf einen Member aus der Visual Basic-Runtimebibliothek verweist, der nicht mit der Kernfunktionalität eingebettet ist, gibt der Compiler einen Fehler zurück, der angibt, dass der Member nicht verfügbar ist.  
  
## <a name="referencing-a-specified-library"></a>Verweisen auf eine angegebene Bibliothek  

 Sie können das `path`-Argument verwenden, um anstelle der Visual Basic-Standardruntimebibliothek mit einem Verweis auf eine benutzerdefinierte Runtimebibliothek zu kompilieren.  
  
 Wenn der Wert für das `path`-Argument ein vollqualifizierter Pfad zu einer DLL ist, verwendet der Compiler diese Datei als Runtimebibliothek. Wenn der Wert für das `path`-Argument kein vollqualifizierter Pfad zu einer DLL ist, sucht der Visual Basic-Compiler zuerst nach der identifizierten DLL im aktuellen Ordner. Anschließend wird der Pfad, den Sie angegeben haben, mithilfe der Compileroption [-sdkpath](sdkpath.md) gesucht. Wenn die `-sdkpath`-Compileroption nicht verwendet wird, sucht der Compiler nach der identifizierten DLL im .NET Framework-Ordner (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie die `-vbruntime`-Option verwendet wird, um mit einem Verweis auf eine benutzerdefinierte Bibliothek zu kompilieren.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic Core: Neuer Kompilierungsmodus in Visual Studio 2010 SP1](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
- [-sdkpath](sdkpath.md)
