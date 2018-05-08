---
title: Beispiele für Kompilierungsbefehlszeilen (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b0f1fc1d269801efdbf2e89d10679dc8159851f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Beispiel für Kompilierungsbefehlszeilen (Visual Basic)
Als Alternative zum Kompilieren von Visual Basic-Programmen in Visual Studio können Sie über die Befehlszeile, um ausführbare Dateien (.exe) oder Dynamic Link Library (DLL) Dateien kompilieren.  
  
 Die Visual Basic-Befehlszeilencompiler unterstützt einen vollständigen Satz von Optionen, die Steuerung von Eingabe- und Ausgabedateien, Assemblys und Debug und Präprozessor Optionen. Jede Option steht in zwei austauschbar Formen: `-option` und `/option`. Diese Dokumentation zeigt nur die `-option` Form.  
  
 Die folgende Tabelle enthält einige Beispielbefehlszeilen, die Sie für Ihre eigenen Zwecke ändern können.  
  
|Beschreibung|Mit|  
|--------|---------|  
|Kompilieren Sie "File.vb" verwenden und Erstellen von File.exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|Kompilieren Sie "File.vb" verwenden, und Erstellen von File.dll.|`vbc -target:library File.vb`|  
|Kompilieren Sie "File.vb" verwenden und Erstellen von My.exe|`vbc -out:My.exe File.vb`|  
|Kompilieren Sie "File.vb" verwenden, und erstellen Sie eine Bibliothek und eine Verweisassembly mit dem Namen "Datei.dll"|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Kompilieren Sie alle Visual Basic-Dateien im aktuellen Verzeichnis mit aktivierten Optimierungen auf und die `DEBUG` Symbol definiert ist, erzeugt File2.exe|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|Kompilieren Sie alle Visual Basic-Dateien im aktuellen Verzeichnis, wodurch eine Debugversion von File2.dll ohne das Logo oder Warnungen|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|Kompilieren Sie alle Visual Basic-Dateien im aktuellen Verzeichnis zu Something.dll|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  Beim Erstellen eines Projekts mit Visual Studio-IDE können Sie Informationen zum zugehörigen anzeigen **Vbc** mit seiner Compileroptionen im Fenster "Ausgabe". Öffnen Sie zum Anzeigen dieser Informationen die [Optionen (Dialogfeld), Projekte und Projektmappen, erstellen und ausführen](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann die **MSBuild-Projektbuilds Ausgabe Ausführlichkeit** auf **Normal** oder ein höheres Maß an Ausführlichkeit.   
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
