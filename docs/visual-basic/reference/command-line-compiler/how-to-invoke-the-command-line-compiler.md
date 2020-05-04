---
title: 'Vorgehensweise: Aufrufen des Befehlszeilencompilers'
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments
- vbc.exe
- Visual Basic compiler, starting
- command line [Visual Basic], arguments
ms.assetid: 0fd9a8f6-f34e-4c35-a49d-9b9bbd8da4a9
ms.openlocfilehash: 3b34ebba68c9c9b2a8335822d0ffaef2a9b06d7c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344261"
---
# <a name="how-to-invoke-the-command-line-compiler-visual-basic"></a>Vorgehensweise: Aufrufen des Befehlszeilencompilers (Visual Basic)

Sie können den Befehlszeilencompiler aufrufen, indem Sie den Namen der ausführbaren Datei in die Befehlszeile eingeben (auch bekannt als MS-DOS-Eingabeaufforderung). Wenn Sie über die Windows-Standardeingabeaufforderung kompilieren, müssen Sie den vollqualifizierten Pfad zur ausführbaren Datei eingeben. Sie können entweder die Developer-Eingabeaufforderung für Visual Studio verwenden oder die PATH-Umgebungsvariable ändern, um dieses Standardverhalten zu überschreiben. Beide Varianten ermöglichen die Kompilierung aus einem beliebigen Verzeichnis, indem Sie einfach den Compilernamen eingeben.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-invoke-the-compiler-using-the-developer-command-prompt-for-visual-studio"></a>Aufrufen des Compilers mithilfe der Developer-Eingabeaufforderung für Visual Studio

1. Öffnen Sie den Visual Studio Tools-Programmordner in der Microsoft Visual Studio-Programmgruppe.

2. Wenn Visual Studio installiert ist, können Sie die Developer-Eingabeaufforderung für Visual Studio verwenden, um von einem beliebigen Verzeichnis auf Ihrem Computer aus auf den Compiler zuzugreifen.

3. Rufen Sie die Developer-Eingabeaufforderung für Visual Studio auf.

4. Geben Sie in der Befehlszeile `vbc.exe` *sourceFileName* ein, und drücken Sie dann die EINGABETASTE.

    Wenn Sie z. B. den Quellcode in einem Verzeichnis namens `SourceFiles` gespeichert haben, öffnen Sie die Eingabeaufforderung, und geben Sie `cd SourceFiles` ein, um zu diesem Verzeichnis zu wechseln. Wenn das Verzeichnis eine Quelldatei mit dem Namen `Source.vb` enthält, können Sie es durch die Eingabe von `vbc.exe Source.vb` kompilieren.

## <a name="to-set-the-path-environment-variable-to-the-compiler-for-the-windows-command-prompt"></a>Festlegen der PATH-Umgebungsvariable auf den Compiler für die Windows-Eingabeaufforderung fest

1. Verwenden Sie die Windows-Suchfunktion für die Suche nach Vbc.exe auf Ihrem lokalen Datenträger.

    Der genaue Name des Verzeichnisses, in dem sich der Compiler befindet, hängt vom Speicherort des Windows-Verzeichnisses und der installierten Version von „.NET Framework“ ab. Wenn mehr als eine Version von „.NET Framework“ installiert ist, müssen Sie festlegen, welche Version verwendet werden soll (in der Regel die neueste Version).

2. Klicken Sie im **Startmenü** zunächst mit der rechten Maustaste auf **Arbeitsplatz** und dann im Kontextmenü auf **Eigenschaften**.

3. Klicken Sie auf die Registerkarte **Erweitert**und dann auf **Umgebungsvariablen**.

4. Klicken Sie im Bereich **Systemvariablen** in der Liste auf **Pfad** und dann auf **Bearbeiten**.

5. Verschieben Sie im Dialogfeld **Systemvariable bearbeiten** die Einfügemarke an das Ende der Zeichenfolge im Feld **Variablenwert**, und geben Sie ein Semikolon (;) gefolgt vom vollständigen Verzeichnisnamen aus Schritt 1 ein.

6. Klicken Sie auf **OK**, um die Änderungen zu bestätigen und die Dialogfelder zu schließen.

     Nachdem Sie die PATH-Umgebungsvariable geändert haben, können Sie den Visual Basic-Compiler von einem beliebigen Verzeichnis auf dem Computer aus in der Windows-Eingabeaufforderung ausführen.

## <a name="to-invoke-the-compiler-using-the-windows-command-prompt"></a>Aufrufen des Compilers mithilfe der Windows-Eingabeaufforderung

1. Klicken Sie im **Startmenü** auf den Ordner **Zubehör**, und öffnen Sie dann die **Windows-Eingabeaufforderung**.

2. Geben Sie in der Befehlszeile `vbc.exe` *sourceFileName* ein, und drücken Sie dann die EINGABETASTE.

     Wenn Sie z. B. den Quellcode in einem Verzeichnis namens `SourceFiles` gespeichert haben, öffnen Sie die Eingabeaufforderung, und geben Sie `cd SourceFiles` ein, um zu diesem Verzeichnis zu wechseln. Wenn das Verzeichnis eine Quelldatei mit dem Namen `Source.vb` enthält, können Sie es durch die Eingabe von `vbc.exe Source.vb` kompilieren.

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
