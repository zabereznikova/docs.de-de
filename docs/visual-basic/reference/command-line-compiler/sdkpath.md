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
ms.openlocfilehash: 2024ccadb06fdea0c24d9d304c2fe040f8cce1d5
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814327"
---
# <a name="-sdkpath"></a>-sdkpath
Gibt den Speicherort der Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll" an.  
  
## <a name="syntax"></a>Syntax  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Argumente  
 `path`  
 Das Verzeichnis mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" zum Kompilieren verwendet. Dieser Pfad wird nicht überprüft werden, bis es geladen wird. Schließen Sie den Namen des Verzeichnisses in Anführungszeichen (""), wenn sie ein Leerzeichen enthält.  
  
## <a name="remarks"></a>Hinweise  
 Diese Option weist Visual Basic-Compiler die Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll" Dateien von einem nicht standardmäßigen Speicherort zu laden. Die `-sdkpath` Option wurde entwickelt, mit [- Netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). Die [!INCLUDE[Compact](~/includes/compact-md.md)] verwendet andere Versionen dieser Unterstützung Bibliotheken für die Verwendung von Typen und Sprachfunktionen, die nicht gefunden wird, auf den Geräten zu vermeiden.  
  
> [!NOTE]
>  Die `-sdkpath` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren. Die `-sdkpath` Option wird festgelegt, wenn ein Gerät Visual Basic-Projekt geladen wird.  
  
 Sie können angeben, dass der Compiler ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek, mithilfe kompilieren soll der `-vbruntime` -Compileroption. Weitere Informationen finden Sie unter [- Vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `Myfile.vb` mit der [!INCLUDE[Compact](~/includes/compact-md.md)], verwenden die Versionen der Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll" finden Sie in das Standardverzeichnis für die Installation von der [!INCLUDE[Compact](~/includes/compact-md.md)] auf Laufwerk C. Normalerweise verwenden Sie die neueste Version von der [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
