---
title: -win32res (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /win32res
helpviewer_keywords:
- win32res compiler option
- /win32res compiler option [C#]
- -win32res compiler option [C#]
- win32res compiler option [C#]
ms.assetid: 3c33f750-6948-4c7e-a27e-bef98f77255b
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 96583542c62305cbaa5a24f66e9e54ec9b525c90
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="win32res-c-compiler-options"></a>/win32res (C#-Compileroptionen)
Die Option **/win32res** fügt eine win32res-Ressource in die Ausgabedatei ein.  
  
## <a name="syntax"></a>Syntax  
  
```console  
/win32res:filename  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Die Ressourcendatei, die Sie Ihrer Ausgabedatei hinzufügen möchten  
  
## <a name="remarks"></a>Hinweise  
 Eine Win32-Ressourcendatei kann mit dem [Ressourcencompiler](../../language-reference/compiler-options/resource-compiler-option.md) erstellt werden. Der Ressourcencompiler wird gestartet, wenn Sie ein Visual C++-Programm kompilieren. Aus der RC-Datei wird eine RES-Datei erstellt.  
  
 Eine Win32-Ressource kann Versions- oder Bitmapinformationen (Symbolinformationen) enthalten, anhand derer die Anwendung im Datei-Explorer identifiziert werden kann. Wenn sie **/win32res** nicht angeben, generiert der Compiler Versioninformationen auf Grundlage der Assemblyversion  
  
 Schauen Sie sich [/linkresource](../../../csharp/language-reference/compiler-options/linkresource-compiler-option.md) zum Verweisen oder [/resource](../../../csharp/language-reference/compiler-options/resource-compiler-option.md) zum Anfügen einer .NET Framework-Ressourcendatei an  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Anwendung**.  
  
3.  Klicken Sie auf die Schaltfläche **Ressourcendatei**, und wählen Sie die Datei über das Kombinationsfeld aus.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `in.cs`, und fügen Sie die Win32-Ressourcendatei `rf.res` an, um `in.exe` zu erzeugen:  
  
```console  
csc /win32res:rf.res in.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
