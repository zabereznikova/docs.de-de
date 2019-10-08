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
ms.openlocfilehash: cee06adec89aac4b3e3f170df3bf932e466f3070
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004959"
---
# <a name="-win32resource"></a>-win32resource
Fügt eine Win32-Ressourcen Datei in die Ausgabedatei ein.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-win32resource:filename  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Der Name der Ressourcen Datei, die der Ausgabedatei hinzugefügt werden soll. Schließen Sie den Dateinamen in Anführungszeichen ("") ein, wenn dieser ein Leerzeichen enthält.  
  
## <a name="remarks"></a>Hinweise  
 Eine Win32-Ressourcen Datei kann mit dem Microsoft Windows-Ressourcen Compiler (RC) erstellt werden.  
  
 Eine Win32-Ressource kann Versions-oder Bitmapinformationen (Symbol) enthalten, mit deren Hilfe die Anwendung im **Datei-Explorer**identifiziert werden kann. Wenn Sie `-win32resource` nicht angeben, generiert der Compiler Versionsinformationen auf Grundlage der Assemblyversion. Die Optionen "`-win32resource`" und "`-win32icon`" schließen sich gegenseitig aus.  
  
 Weitere Informationen zum Hinzufügen einer .NET Framework Ressourcen Datei finden [Visual Basic](../../../visual-basic/reference/command-line-compiler/resource.md) .NET Framework Sie unter [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) .  
  
> [!NOTE]
> Die Option "`-win32resource`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird `In.vb` kompiliert und eine Win32-Ressourcen Datei, `Rf.res`, angefügt:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
