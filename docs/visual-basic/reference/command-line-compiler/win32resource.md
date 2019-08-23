---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
ms.openlocfilehash: 382dcc6571aa06ecdfc32bf43080c4b7a36eb1f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961304"
---
# <a name="-win32resource"></a>-win32resource
Fügt eine Win32-Ressourcen Datei in die Ausgabedatei ein.  
  
## <a name="syntax"></a>Syntax  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Der Name der Ressourcen Datei, die der Ausgabedatei hinzugefügt werden soll. Schließen Sie den Dateinamen in Anführungszeichen ("") ein, wenn dieser ein Leerzeichen enthält.  
  
## <a name="remarks"></a>Hinweise  
 Eine Win32-Ressourcen Datei kann mit dem Microsoft Windows-Ressourcen Compiler (RC) erstellt werden.  
  
 Eine Win32-Ressource kann Versions-oder Bitmapinformationen (Symbol) enthalten, mit deren Hilfe die Anwendung im **Datei-Explorer**identifiziert werden kann. Wenn Sie nicht angeben `-win32resource`, generiert der Compiler Versionsinformationen auf Grundlage der Assemblyversion. Die `-win32resource` Optionen `-win32icon` und schließen sich gegenseitig aus.  
  
 Weitere Informationen zum Hinzufügen einer .NET Framework Ressourcen Datei finden [Visual Basic](../../../visual-basic/reference/command-line-compiler/resource.md) .NET Framework Sie unter [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) .  
  
> [!NOTE]
> Die `-win32resource` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird `In.vb` `Rf.res`eine Win32-Ressourcen Datei () kompiliert und angefügt:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
