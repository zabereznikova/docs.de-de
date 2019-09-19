---
title: 'Vorgehensweise: Aufrufen des Befehlszeilen Compilers (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: a81d5b4f4eae76b0306e2d27475cb8527bda0ff2
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054220"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Vorgehensweise: Aufrufen des Befehlszeilen Compilers (Visual Basic)

Sie können den Befehlszeilen Compiler aufrufen, indem Sie den Namen seiner ausführbaren Datei in die Befehlszeile eingeben, auch bekannt als MS-DOS-Eingabeaufforderung. Wenn Sie von der standardmäßigen Windows-Eingabeaufforderung kompilieren, müssen Sie den voll qualifizierten Pfad zur ausführbaren Datei eingeben. Um dieses Standardverhalten zu überschreiben, können Sie entweder die Developer-Eingabeaufforderung für Visual Studio verwenden oder die PATH-Umgebungsvariable ändern. Beide ermöglichen die Kompilierung aus einem beliebigen Verzeichnis, indem Sie einfach den Compilernamen eingeben.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a>So rufen Sie den Compiler mithilfe der Developer-Eingabeaufforderung für Visual Studio auf

1. Öffnen Sie den Visual Studio-Tools Programmordner innerhalb der Gruppe Microsoft Visual Studio Programm.

2. Wenn Visual Studio installiert ist, können Sie die Developer-Eingabeaufforderung für Visual Studio verwenden, um von einem beliebigen Verzeichnis auf Ihrem Computer aus auf den Compiler zuzugreifen.

3. Rufen Sie die Developer-Eingabeaufforderung für Visual Studio auf.

4. Geben `vbc.exe` Sie in der Befehlszeile *sourceFileName* ein, und drücken Sie dann die EINGABETASTE.

    Wenn Sie z. b. den Quellcode in einem Verzeichnis mit dem `SourceFiles`Namen gespeichert haben, öffnen Sie die Eingabeaufforderung `cd SourceFiles` , und geben Sie ein, um zu diesem Verzeichnis zu wechseln. Wenn das Verzeichnis eine Quelldatei mit dem `Source.vb`Namen enthält, können Sie es durch `vbc.exe Source.vb`Eingabe von kompilieren.

## <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>So legen Sie die PATH-Umgebungsvariable auf den Compiler für die Windows-Eingabeaufforderung fest

1. Verwenden Sie das Windows-Such Feature, um "Vbc. exe" auf Ihrem lokalen Datenträger zu suchen.

    Der genaue Name des Verzeichnisses, in dem sich der Compiler befindet, hängt vom Speicherort des Windows-Verzeichnisses und von der installierten Version des ".NET Framework" ab. Wenn Sie mehr als eine Version von ".NET Framework" installiert haben, müssen Sie bestimmen, welche Version verwendet werden soll (in der Regel die neueste Version).

2. Klicken Sie im **Startmenü** mit der rechten Maustaste auf **Arbeitsplatz**, und klicken Sie dann im Kontextmenü auf **Eigenschaften** .

3. Klicken Sie auf die Registerkarte **erweitert** , und klicken Sie dann auf **Umgebungsvariablen**.

4. Wählen Sie im Bereich **System** Variablen den **Pfad** in der Liste aus, und klicken Sie auf **Bearbeiten**.

5. Verschieben Sie im Dialogfeld **System Variable bearbeiten** die Einfügemarke an das Ende der Zeichenfolge im Feld **Variablen Wert** , und geben Sie ein Semikolon (;) gefolgt vom vollständigen Verzeichnisnamen, der in Schritt 1 gefunden wurde.

6. Klicken Sie auf **OK** , um die Änderungen zu bestätigen und die Dialogfelder zu schließen.

     Nachdem Sie die PATH-Umgebungsvariable geändert haben, können Sie den Visual Basic-Compiler an der Windows-Eingabeaufforderung von einem beliebigen Verzeichnis auf dem Computer ausführen.

## <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>So rufen Sie den Compiler mithilfe der Windows-Eingabeaufforderung auf

1. Klicken Sie im **Startmenü** auf den Ordner **Zubehör** , und öffnen Sie dann die **Windows-Eingabeaufforderung**.

2. Geben `vbc.exe`Sie in der Befehlszeile *sourceFileName* ein, und drücken Sie dann die EINGABETASTE.

     Wenn Sie z. b. den Quellcode in einem Verzeichnis mit dem `SourceFiles`Namen gespeichert haben, öffnen Sie die Eingabeaufforderung `cd SourceFiles` , und geben Sie ein, um zu diesem Verzeichnis zu wechseln. Wenn das Verzeichnis eine Quelldatei mit dem `Source.vb`Namen enthält, können Sie es durch `vbc.exe Source.vb`Eingabe von kompilieren.

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
