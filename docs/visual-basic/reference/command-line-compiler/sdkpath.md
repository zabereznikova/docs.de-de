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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 162c7d58350c381ec667e8a4cd11c03e83fcdf44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-sdkpath"></a>-sdkpath
Gibt den Speicherort der Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll" an.  
  
## <a name="syntax"></a>Syntax  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Argumente  
 `path`  
 Das Verzeichnis mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" zum Kompilieren verwendet. Dieser Pfad wird nicht überprüft werden, bis es geladen wird. Setzen Sie den Namen des Verzeichnisses in Anführungszeichen (""), wenn es sich um ein Leerzeichen enthält.  
  
## <a name="remarks"></a>Hinweise  
 Diese Option weist den Visual Basic-Compiler die Datei "mscorlib.dll" und "Microsoft.VisualBasic.dll" Dateien von einem nicht standardmäßigen Speicherort zu laden. Die `-sdkpath` wurde bei Verwendung der Option mit [- Netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). Die [!INCLUDE[Compact](~/includes/compact-md.md)] verwendet verschiedene Versionen dieser unterstützen, Bibliotheken, um die Verwendung von Datentypen und Sprachfunktionen, die nicht gefunden wird, auf den Geräten zu vermeiden.  
  
> [!NOTE]
>  Die `-sdkpath` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren. Die `-sdkpath` Option wird festgelegt, wenn ein Gerät Visual Basic-Projekt geladen wird.  
  
 Sie können angeben, dass der Compiler ohne einen Verweis auf die Visual Basic-Laufzeitbibliothek, mithilfe kompilieren soll der `-vbruntime` -Compileroption. Weitere Informationen finden Sie unter [- Vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `Myfile.vb` mit der [!INCLUDE[Compact](~/includes/compact-md.md)], mit den Versionen von "mscorlib.dll" und "Microsoft.VisualBasic.dll" in das Standardverzeichnis für die Installation der gefunden die [!INCLUDE[Compact](~/includes/compact-md.md)] auf Laufwerk C. Normalerweise verwenden Sie die neueste Version von der [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
