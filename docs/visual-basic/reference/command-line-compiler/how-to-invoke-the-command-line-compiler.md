---
title: 'Gewusst wie: Aufrufen des Befehlszeilencompilers (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c69860ede5620272e67bde435e6e6fa08cc81bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Gewusst wie: Aufrufen des Befehlszeilencompilers (Visual Basic)
Durch den Namen seiner ausführbaren Datei in der Befehlszeile, auch bekannt als MS-DOS, können Sie den Befehlszeilencompiler aufrufen. Wenn Sie über die standardmäßige Windows-Befehlszeile kompilieren, müssen Sie den vollqualifizierten Pfad zur ausführbaren Datei eingeben. Um dieses Standardverhalten zu überschreiben, können Sie entweder die [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] -Eingabeaufforderung ein, oder ändern Sie die PATH-Umgebungsvariable. Beide können Sie aus dem Verzeichnis zu kompilieren, indem Sie einfach den Compilernamen.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-visual-studio-command-prompt"></a>Zum Aufrufen des Compilers über die Visual Studio-Eingabeaufforderung  
  
1.  Öffnen Sie den Programmordner Visual Studio-Tools in der Programmgruppe Microsoft Visual Studio.  
  
2.  Sie können die [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Befehlszeile aus, um den Compiler aus einem beliebigen Verzeichnis auf Ihrem Computer zugreifen, wenn Visual Studio installiert ist.  
  
3.  Aufrufen der [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Eingabeaufforderung.  
  
4.  Geben Sie an der Befehlszeile `vbc.exe` *Quelldateiname* und drücken Sie dann die EINGABETASTE.  
  
     Angenommen, wenn Sie den Quellcode in einem Verzeichnis namens gespeichert `SourceFiles`, öffnen Sie die Eingabeaufforderung, und geben `cd SourceFiles` so ändern Sie in diesem Verzeichnis. Wenn das Verzeichnis eine Quelldatei mit dem Namen enthalten `Source.vb`, könnten durch eingeben Kompilieren `vbc.exe Source.vb`.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>PATH-Umgebungsvariable festlegen, an den Compiler für die Windows-Befehlszeile  
  
1.  Verwenden Sie die Windows-Suchfunktion Vbc.exe auf dem lokalen Datenträger gefunden.  
  
     Der genaue Name des Verzeichnisses auf dem sich der Compiler befindet hängt davon ab, den Speicherort des Windows-Verzeichnisses und die Version von ".NET Framework" installiert. Wenn Sie mehr als eine Version von ".NET Framework" installiert haben, müssen Sie die Version, verwenden Sie (in der Regel die neueste Version) ermitteln.  
  
2.  Aus Ihrer **starten** im Menü mit der rechten Maustaste **Arbeitsplatz**, und klicken Sie dann auf **Eigenschaften** aus dem Kontextmenü.  
  
3.  Klicken Sie auf die **erweitert** Registerkarte, und klicken Sie dann auf **Umgebungsvariablen**.  
  
4.  In der **System** Variablen (Bereich), wählen **Pfad** aus der Liste und klicken Sie auf **bearbeiten**.  
  
5.  In der **bearbeiten System** Variable Dialogfeld verschieben Sie die Einfügemarke an das Ende der Zeichenfolge in der **Variablenwert** ein und geben Sie ein Semikolon (;) gefolgt von der vollständiger Verzeichnisname, der in Schritt 1 gefunden.  
  
6.  Klicken Sie auf **OK** die Bearbeitungen bestätigt und die Dialogfelder zu schließen.  
  
     Nachdem Sie der PATH-Umgebungsvariablen ändern, können Sie Ausführen den [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler an der Windows-Eingabeaufforderung aus dem Verzeichnis auf dem Computer.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Zum Aufrufen des Compilers über die Windows-Eingabeaufforderung  
  
1.  Aus der **starten** Menü klicken Sie auf die **Zubehör** Ordner, und öffnen Sie dann die **Windows-Befehlszeile**.  
  
2.  Geben Sie an der Befehlszeile `vbc.exe` *Quelldateiname* und drücken Sie dann die EINGABETASTE.  
  
     Angenommen, wenn Sie den Quellcode in einem Verzeichnis namens gespeichert `SourceFiles`, öffnen Sie die Eingabeaufforderung, und geben `cd SourceFiles` so ändern Sie in diesem Verzeichnis. Wenn das Verzeichnis eine Quelldatei mit dem Namen enthalten `Source.vb`, könnten durch eingeben Kompilieren `vbc.exe Source.vb`.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
