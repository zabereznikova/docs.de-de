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
ms.openlocfilehash: 0771ed41d6c58ce7cc98435b405f5819e45393db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916759"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Beispiel für Kompilierungsbefehlszeilen (Visual Basic)
Als Alternative zum Kompilieren von Visual Basic-Programmen in Visual Studio können Sie über die Befehlszeile, ausführbare Dateien (.exe) oder Dynamic Link Library (DLL) Dateien kompilieren.  
  
 Die Visual Basic-Befehlszeilencompiler unterstützt einen vollständigen Satz von Optionen, die Steuerung von Eingabe- und Ausgabedateien, Assemblys und Debuggen und Präprozessoroptionen an. Jede Option ist in zwei austauschbar Varianten verfügbar: `-option` und `/option`. In dieser Dokumentation wird nur die `-option` Formular.  
  
 Die folgende Tabelle enthält einige Beispielbefehlszeilen, die Sie für Ihre eigenen Zwecke ändern können.  
  
|Beschreibung|Mit|  
|--------|---------|  
|Kompilieren Sie VB-Datei zu und erstellen Sie File.exe|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|VB-Datei zu kompilieren und Erstellen von File.dll|`vbc -target:library File.vb`|  
|Kompilieren Sie VB-Datei zu und erstellen Sie My.exe|`vbc -out:My.exe File.vb`|  
|Kompilieren Sie VB-Datei zu und erstellen Sie einer Bibliothek und eine Verweisassembly mit dem Namen File.dll|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Kompilieren Sie alle Visual Basic-Dateien im aktuellen Verzeichnis mit aktivierten Optimierungen auf und die `DEBUG` Symbol definiert ist, erzeugt File2.exe|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|Kompilieren Sie alle Visual Basic-Dateien im aktuellen Verzeichnis, erzeugen eine Debugversion von File2.dll erstellt wird, ohne das Logo oder Warnungen|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|Kompilieren Sie alle Visual Basic-Dateien im aktuellen Verzeichnis zu Something.dll|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  Wenn Sie ein Projekt mithilfe von Visual Studio-IDE erstellen, können Sie anzeigen, Informationen über die zugeordnete **Vbc** Befehl seine Compileroptionen im Ausgabefenster angezeigt. Um diese Informationen anzuzeigen, öffnen Sie die [Optionen (Dialogfeld), Projekte und Projektmappen, erstellen und ausführen](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann die **MSBuild Projektbuildausgabe** zu **Normal** oder ein höheres Maß an Ausführlichkeit.   
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
