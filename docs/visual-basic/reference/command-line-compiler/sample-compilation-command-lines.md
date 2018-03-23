---
title: Beispiele für Kompilierungsbefehlszeilen (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf20e2916efd2eb10065be22c319e34ddb2bda9a
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2018
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Beispiel für Kompilierungsbefehlszeilen (Visual Basic)
Als Alternative zum Kompilieren von Visual Basic-Programmen in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], können Sie kompilieren über die Befehlszeile, um ausführbare Dateien (.exe) oder Dynamic Link Library (DLL)-Dateien zu erzeugen.  
  
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
