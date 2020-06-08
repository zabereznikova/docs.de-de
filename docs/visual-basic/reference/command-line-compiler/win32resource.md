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
ms.openlocfilehash: bcbc690690993a094bc5360d0c13bddebf8cd615
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414245"
---
# <a name="-win32resource"></a>-win32resource
Fügt eine Win32-Ressourcendatei in die Ausgabedatei ein  
  
## <a name="syntax"></a>Syntax  
  
```console  
-win32resource:filename  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Der Name der Ressourcendatei, die der Ausgabedatei hinzugefügt werden soll. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie diesen in Anführungszeichen (" ") einschließen.  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine Win32-Ressourcendatei mit dem Windows-Ressourcencompiler (RC) erstellen.  
  
 Eine Win32-Ressource kann Versions- oder Bitmapinformationen (Symbolinformationen) enthalten, anhand derer die Anwendung in **Datei-Explorer** identifiziert werden kann. Wenn Sie `-win32resource` nicht angeben, generiert der Compiler Versionsinformationen auf Grundlage der Assemblyversion. Die Optionen `-win32resource` und `-win32icon` schließen sich gegenseitig aus.  
  
 Weitere Informationen zum Verweis auf eine .NET Framework-Ressourcendatei finden Sie unter [-linkresource (Visual Basic)](linkresource.md). Informationen zum Hinzufügen einer .NET Framework-Ressourcendatei finden Sie unter [-resource (Visual Basic)](resource.md).  
  
> [!NOTE]
> Diese Option `-win32resource` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code werden `In.vb` kompiliert und die Win32-Ressourcendatei `Rf.res` angefügt:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
