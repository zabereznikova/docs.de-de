---
title: 'Assembly wurde nicht generiert: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: c088f273c100b1a7eefcf74047865093f378e970
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161659"
---
# <a name="bc30145-unable-to-emit-assembly-error-message"></a>BC30145: die Assembly kann nicht ausgegeben werden: \<error message>

Der Visual Basic-Compiler ruft den Assemblylinker (*Al.exe*, auch bekannt als ALink) auf, um eine Assembly mit einem Manifest zu generieren, und der Linker meldet einen Fehler in der Ausgabe Phase der Erstellung der Assembly.

**Fehler-ID:** BC30145

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Überprüfen Sie die Fehlermeldung in Anführungszeichen, und informieren Sie sich im Thema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) über weitere Erläuterungen und Ratschläge.

2. Versuchen Sie, die Assembly manuell zu signieren, indem Sie entweder die [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) oder das [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)verwenden.

3. Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.

### <a name="to-sign-the-assembly-manually"></a>So signieren Sie die Assembly manuell

1. Verwenden Sie die [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)), um eine Datei mit einem öffentlichen/privaten Schlüsselpaar zu erstellen.

   Diese Datei hat die Erweiterung " *. snk* ".

2. Löschen Sie den COM-Verweis, der für den Fehler verantwortlich ist, aus Ihrem Projekt.

3. Öffnen Sie die [Developer-Eingabeaufforderung für Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).

   Geben Sie in Windows 10 die **Developer-Eingabeaufforderung** in das Suchfeld auf der Taskleiste ein. Wählen Sie dann in der Ergebnisliste **Developer-Eingabeaufforderung für vs 2017** aus.

4. Wechseln Sie in das Verzeichnis, in dem Sie den Assemblywrapper platzieren möchten.

5. Geben Sie den folgenden Befehl ein:

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   Ein Beispiel für den eigentlichen Befehl, den Sie eingeben können, ist:

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > Verwenden Sie doppelte Anführungszeichen, wenn ein Pfad oder eine Datei Leerzeichen enthält.

6. Fügen Sie in Visual Studio einen .net-Assemblyverweis auf die soeben erstellte Datei hinzu.

## <a name="see-also"></a>Siehe auch

- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)
- [How to: Erstellen eines öffentlichen/privaten Schlüsselpaars](../../../standard/assembly/create-public-private-key-pair.md)
- [Sprechen Sie mit uns](/visualstudio/ide/feedback-options)
