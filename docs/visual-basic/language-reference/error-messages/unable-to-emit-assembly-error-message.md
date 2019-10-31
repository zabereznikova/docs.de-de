---
title: 'Assembly wurde nicht generiert: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 5776755a57fbc2b0086b1c9b6cfbb2f2b7eb03fa
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197274"
---
# <a name="unable-to-emit-assembly-error-message"></a>Die Assembly kann nicht ausgegeben werden: \<Fehlermeldung >

Der Visual Basic-Compiler ruft den Assemblylinker (*Al. exe*, auch bekannt als ALink) auf, um eine Assembly mit einem Manifest zu generieren, und der Linker meldet einen Fehler in der Ausgabe Phase der Erstellung der Assembly.

**Fehler-ID:** BC30145

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Überprüfen Sie die Fehlermeldung in Anführungszeichen, und lesen Sie das Thema " [Al. exe](../../../framework/tools/al-exe-assembly-linker.md) ".

2. Versuchen Sie, die Assembly manuell zu signieren, indem Sie entweder " [Al. exe](../../../framework/tools/al-exe-assembly-linker.md) " oder " [Sn. exe" (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)verwenden.

3. Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.

### <a name="to-sign-the-assembly-manually"></a>So signieren Sie die Assembly manuell

1. Verwenden Sie " [Sn. exe" (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)), um eine Datei mit einem öffentlichen/privaten Schlüsselpaar zu erstellen.

   Diese Datei hat die Erweiterung " *. snk* ".

2. Löschen Sie den COM-Verweis, der für den Fehler verantwortlich ist, aus Ihrem Projekt.

3. Öffnen Sie die [Developer-Eingabeaufforderung für Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).

   Geben Sie in Windows 10 die **Developer-Eingabeaufforderung** in das Suchfeld auf der Taskleiste ein. Wählen Sie dann in der Ergebnisliste **Developer-Eingabeaufforderung für vs 2017** aus.

4. Wechseln Sie in das Verzeichnis, in dem Sie den Assemblywrapper platzieren möchten.

5. Geben Sie folgenden Befehl ein:

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

- ["Al. exe"](../../../framework/tools/al-exe-assembly-linker.md)
- [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)
- [Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars](../../../standard/assembly/create-public-private-key-pair.md)
- [Sprechen Sie mit uns](/visualstudio/ide/feedback-options)
