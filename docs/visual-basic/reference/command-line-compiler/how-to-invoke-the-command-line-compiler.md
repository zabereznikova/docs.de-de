---
title: 'Vorgehensweise: Aufrufen des Befehlszeilencompilers (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: d2d193f8c3d483ff87fe719919982e8c3473ec0b
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221842"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Vorgehensweise: Aufrufen des Befehlszeilencompilers (Visual Basic)
Sie können den Befehlszeilencompiler aufrufen, geben Sie den Namen seiner ausführbaren Datei in die Befehlszeile, auch bekannt als die MS-DOS-Eingabeaufforderung. Wenn Sie von der Standard-Windows-Eingabeaufforderung kompilieren, müssen Sie den vollqualifizierten Pfad zur ausführbaren Datei eingeben. Um dieses Standardverhalten zu überschreiben, können Sie entweder verwenden die Developer-Eingabeaufforderung für Visual Studio, oder Ändern der Umgebungsvariablen PATH enthalten. Beide können Sie aus dem Verzeichnis zu kompilieren, indem Sie einfach den Compilernamen.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a>Zum Aufrufen des Compilers, die mit der Developer-Eingabeaufforderung für Visual Studio  
  
1.  Der Programmordner des Visual Studio-Tools in der Programmgruppe Microsoft Visual Studio zu öffnen.  
  
2.  Sie können ein Developer-Eingabeaufforderung für Visual Studio verwenden, den Compiler aus dem Verzeichnis auf Ihrem Computer, den Zugriff auf, wenn Visual Studio installiert ist.  
  
3.  Rufen Sie die Developer-Eingabeaufforderung für Visual Studio.  
  
4.  Geben Sie an der Befehlszeile `vbc.exe` *"sourceFileName"* und drücken Sie dann die EINGABETASTE.  
  
     Z. B., wenn Sie Ihren Quellcode in einem Verzeichnis namens gespeichert `SourceFiles`, öffnen Sie die Eingabeaufforderung und geben `cd SourceFiles` so ändern Sie in diesem Verzeichnis. Wenn das Verzeichnis eine Quellcodedatei namens enthalten `Source.vb`, können Sie diese kompilieren, indem Sie eingeben `vbc.exe Source.vb`.  
  
### <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Der PATH-Umgebungsvariable festlegen, an den Compiler für die Windows-Eingabeaufforderung  
  
1.  Verwenden Sie die Windows Search-Funktion, um Vbc.exe auf dem lokalen Datenträger suchen.  
  
     Der genaue Name des Verzeichnisses, in denen der Compiler befindet, hängt davon ab, der Speicherort des Windows-Verzeichnisses und die Version von ".NET Framework" installiert. Wenn Sie mehr als eine Version von ".NET Framework" installiert haben, müssen Sie feststellen, welcher Version (in der Regel die neueste Version) verwendet wird.  
  
2.  Aus Ihrem **starten** im Menü mit der rechten Maustaste **Arbeitsplatz**, und klicken Sie dann auf **Eigenschaften** aus dem Kontextmenü.  
  
3.  Klicken Sie auf die **erweitert** Registerkarte, und klicken Sie dann auf **Umgebungsvariablen**.  
  
4.  In der **System** wählen Sie im Variablenbereich **Pfad** aus der Liste und klicken Sie auf **bearbeiten**.  
  
5.  In der **bearbeiten System** Variable Dialogfeld Verschieben der Einfügemarke bis zum Ende der Zeichenfolge in die **Variablenwert** ein, und geben Sie ein Semikolon (;) gefolgt von der vollständigen Verzeichnisnamen, die in Schritt 1.  
  
6.  Klicken Sie auf **OK** die Bearbeitungen bestätigt und die Dialogfelder zu schließen.  
  
     Nachdem Sie der PATH-Umgebungsvariablen ändern, können Sie Visual Basic-Compiler an der Windows-Eingabeaufforderung aus dem Verzeichnis auf dem Computer ausführen.  
  
### <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Zum Aufrufen des Compilers mithilfe der Windows-Eingabeaufforderung  
  
1.  Von der **starten** Menü klicken Sie auf die **Zubehör** Ordner, und öffnen Sie die **Windows-Eingabeaufforderung**.  
  
2.  Geben Sie an der Befehlszeile `vbc.exe` *"sourceFileName"* und drücken Sie dann die EINGABETASTE.  
  
     Z. B., wenn Sie Ihren Quellcode in einem Verzeichnis namens gespeichert `SourceFiles`, öffnen Sie die Eingabeaufforderung und geben `cd SourceFiles` so ändern Sie in diesem Verzeichnis. Wenn das Verzeichnis eine Quellcodedatei namens enthalten `Source.vb`, können Sie diese kompilieren, indem Sie eingeben `vbc.exe Source.vb`.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
