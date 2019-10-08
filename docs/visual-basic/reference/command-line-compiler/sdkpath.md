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
ms.openlocfilehash: 46cec7ac3cb78c4fc97e299535f9085eff6daeff
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004695"
---
# <a name="-sdkpath"></a>-sdkpath
Gibt den Speicherort von "mscorlib. dll" und "Microsoft. VisualBasic. dll" an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Argumente  
 `path`  
 Das Verzeichnis mit den Versionen von "mscorlib. dll" und "Microsoft. VisualBasic. dll", die für die Kompilierung verwendet werden sollen. Dieser Pfad wird erst überprüft, wenn er geladen wurde. Schließen Sie den Verzeichnisnamen in Anführungszeichen ("") ein, wenn dieser ein Leerzeichen enthält.  
  
## <a name="remarks"></a>Hinweise  
 Diese Option weist den Visual Basic Compiler an, die Dateien "mscorlib. dll" und "Microsoft. VisualBasic. dll" von einem nicht standardmäßigen Speicherort zu laden. Die Option "`-sdkpath`" wurde für die Verwendung mit [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)entwickelt. In der .NET Compact Framework werden verschiedene Versionen dieser Unterstützungs Bibliotheken verwendet, um die Verwendung von Typen und sprach Features zu vermeiden, die auf den Geräten nicht gefunden werden.  
  
> [!NOTE]
> Die Option "`-sdkpath`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren. Die Option "`-sdkpath`" wird festgelegt, wenn ein Visual Basic Geräte Projekt geladen wird.  
  
 Sie können angeben, dass der Compiler ohne einen Verweis auf die Visual Basic Lauf Zeit Bibliothek kompilieren soll, indem Sie die `-vbruntime`-Compileroption verwenden. Weitere Informationen finden Sie unter [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird `Myfile.vb` mit dem .NET Compact Framework kompiliert. dabei werden die Versionen von "mscorlib. dll" und "Microsoft. VisualBasic. dll" verwendet, die im Standard Installationsverzeichnis der .NET Compact Framework auf Laufwerk C gefunden werden. Normalerweise verwenden Sie die neueste Version der .NET Compact Framework.  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
