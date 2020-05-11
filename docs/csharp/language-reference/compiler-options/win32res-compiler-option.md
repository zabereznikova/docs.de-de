---
title: -win32res (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /win32res
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
ms.openlocfilehash: 3bb1614fcf28c62a9000c9b96af2f046f329fb1e
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794376"
---
# <a name="-win32res-c-compiler-options"></a>-win32res (C#-Compileroptionen)
Die Option **-win32res** fügt eine Win32-Ressource in die Ausgabedatei ein.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-win32res:filename  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Die Ressourcendatei, die Sie Ihrer Ausgabedatei hinzufügen möchten  
  
## <a name="remarks"></a>Hinweise  
 Eine Win32-Ressourcendatei kann mit dem [Ressourcencompiler](resource-compiler-option.md) erstellt werden. Der Ressourcencompiler wird gestartet, wenn Sie ein Visual C++-Programm kompilieren. Aus der RC-Datei wird eine RES-Datei erstellt.  
  
 Eine Win32-Ressource kann Versions- oder Bitmapinformationen (Symbolinformationen) enthalten, anhand derer die Anwendung im Datei-Explorer identifiziert werden kann. Wenn sie **-win32res** nicht angeben, generiert der Compiler Versionsinformationen auf Grundlage der Assemblyversion.  
  
 Weitere Informationen zum Verweisen auf eine .NET Framework-Ressourcendatei finden Sie unter [-linkresource](./linkresource-compiler-option.md), weitere Informationen zum Anfügen einer .NET Framework-Ressourcendatei unter [-resource](./resource-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2. Klicken Sie auf die Eigenschaftenseite **Anwendung**.  
  
3. Klicken Sie auf die Schaltfläche **Ressourcendatei**, und wählen Sie die Datei über das Kombinationsfeld aus.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `in.cs`, und fügen Sie die Win32-Ressourcendatei `rf.res` an, um `in.exe` zu erzeugen:  
  
```console  
csc -win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
