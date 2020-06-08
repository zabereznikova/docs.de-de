---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
ms.openlocfilehash: 85aba17b330af1b25b39f462844bc1a4856a448a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403108"
---
# <a name="-sdkpath"></a>-sdkpath
Gibt den Speicherort von „mscorlib.dll“ und „microsoft.visualbasic.dll“ an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Argumente  
 `path`  
 Das Verzeichnis mit den Versionen von „mscorlib.dll“ und „Microsoft.VisualBasic.dll“, die für die Kompilierung verwendet werden sollen. Dieser Pfad wird erst überprüft, wenn er geladen wurde. Wenn der Verzeichnisname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.  
  
## <a name="remarks"></a>Hinweise  
 Diese Option weist den Visual Basic-Compiler an, die Dateien „mscorlib.dll“ und „Microsoft.VisualBasic.dll“ von einem Speicherort zu laden, der nicht dem Standardpfad entspricht. Die `-sdkpath`-Option wurde für die Verwendung mit [-netcf](netcf.md) konzipiert. In .NET Compact Framework werden verschiedene Versionen dieser Unterstützungsbibliotheken verwendet, um die Verwendung von Typen und Sprachfeatures zu vermeiden, die auf den Geräten nicht gefunden werden.  
  
> [!NOTE]
> Die Option `-sdkpath` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren. Die Option `-sdkpath` wird festgelegt, wenn ein Visual Basic-Geräteprojekt geladen wird.  
  
 Sie können angeben, dass der Compiler ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek kompilieren soll, indem Sie die Compileroption `-vbruntime` verwenden. Weitere Informationen finden Sie unter [-vbruntime](vbruntime.md).  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird `Myfile.vb` mit .NET Compact Framework kompiliert. Dabei werden die Versionen von „mscorlib.dll“ und „Microsoft.VisualBasic.dll“ verwendet, die im Standardinstallationsverzeichnis von .NET Compact Framework auf Laufwerk C: gefunden werden. Normalerweise verwenden Sie die neueste Version von .NET Compact Framework.  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
- [-netcf](netcf.md)
- [-vbruntime](vbruntime.md)
