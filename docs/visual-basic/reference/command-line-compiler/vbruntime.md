---
title: / vbruntime | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- /vbruntime
dev_langs:
- VB
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 455f950988b540b74874ce38882c59059f77ea8f
ms.lasthandoff: 03/13/2017

---
# <a name="vbruntime"></a>/vbruntime
Gibt an, dass der Compiler ohne einen Verweis auf die Visual Basic Runtime Library oder mit einem Verweis auf eine bestimmte Laufzeitbibliothek kompilieren soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
/vbruntime:{ - | + | * | path }  
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
 Die `/vbruntime` -Compileroption können Sie angeben, dass der Compiler ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren soll. Wenn Sie ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren, werden Fehler oder Warnungen auf Code oder Sprache Konstrukten protokolliert, die einen Aufruf einer Visual Basic-Laufzeithilfsfunktion zu generieren. (Ein *Visual Basic-Laufzeithilfsfunktion* ist eine Funktion definiert, die in Microsoft.VisualBasic.dll, die zur Laufzeit, um eine bestimmte Sprachsemantik auszuführen aufgerufen wird.)  
  
 Die `/vbruntime+` Option führt zum selben Verhalten, das auftritt, wenn kein `/vbruntime` -Schalter angegeben ist. Können Sie die `/vbruntime+` Option zum Überschreiben von vorherigen `/vbruntime` Switches.  
  
 Die meisten Objekte von der `My` Typ sind nicht verfügbar, wenn Sie verwenden die `/vbruntime-` oder `vbruntime:``path` Optionen.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Einbetten von Visual Basic-Laufzeit-Kernfunktionalität  
 Die `/vbruntime*` Option können Sie ohne einen Verweis auf eine Laufzeitbibliothek kompilieren. Stattdessen ist Kernfunktionalität aus der Visual Basic-Laufzeitbibliothek in der Benutzerassembly eingebettet. Sie können diese Option verwenden, wenn Ihre Anwendung auf Plattformen ausgeführt wird, die die Visual Basic-Laufzeit nicht enthalten.  
  
 Die folgenden Elemente für die Common Language Runtime eingebettet werden:  
  
-   <xref:Microsoft.VisualBasic.CompilerServices.Conversions>Klasse</xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>Methode</xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>Methode</xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
-   <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>Methode</xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack>Konstante</xref:Microsoft.VisualBasic.Constants.vbBack>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr>Konstante</xref:Microsoft.VisualBasic.Constants.vbCr>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf>Konstante</xref:Microsoft.VisualBasic.Constants.vbCrLf>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed>Konstante</xref:Microsoft.VisualBasic.Constants.vbFormFeed>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf>Konstante</xref:Microsoft.VisualBasic.Constants.vbLf>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine>Konstante</xref:Microsoft.VisualBasic.Constants.vbNewLine>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar>Konstante</xref:Microsoft.VisualBasic.Constants.vbNullChar>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString>Konstante</xref:Microsoft.VisualBasic.Constants.vbNullString>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab>Konstante</xref:Microsoft.VisualBasic.Constants.vbTab>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>Konstante</xref:Microsoft.VisualBasic.Constants.vbVerticalTab>  
  
-   Einige Objekte von der `My` Typ  
  
 Bei der Kompilierung mit der `/vbruntime*` -Option, und der Code verweist auf ein Element aus der Visual Basic-Laufzeitbibliothek, die nicht mit den Kernfunktionen eingebettet ist, gibt der Compiler einen Fehler, der angibt, dass der Member nicht verfügbar ist.  
  
## <a name="referencing-a-specified-library"></a>Verweisen auf eine angegebene Bibliothek  
 Sie können die `path` Argument mit einem Verweis auf eine benutzerdefinierte Laufzeitbibliothek anstelle der standardmäßigen Visual Basic-Laufzeitbibliothek kompilieren.  
  
 Wenn der Wert für das `path` -Argument einen vollqualifizierten Pfad zu einer DLL ist, verwendet der Compiler diese Datei als Laufzeitbibliothek. Wenn der Wert für das `path` -Argument keinen vollqualifizierten Pfad zu einer DLL, die Visual Basic-Compiler wird zuerst nach der angegebenen DLL im aktuellen Ordner suchen. Danach sucht in den Pfad, die Sie angegeben haben die [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) (Compileroption). Wenn die `/sdkpath` -Compileroption nicht verwendet wird, sucht der Compiler nach der angegebenen DLL im .NET Framework-Ordner (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die `/vbruntime` Option einen Verweis auf eine benutzerdefinierte Bibliothek zu kompilieren.  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Core – neue Kompilierungsmodus in Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)   
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
