---
title: 'Assembly wurde nicht generiert: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: d564f4f4462a691504297d65575956c5f06691ca
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759222"
---
# <a name="unable-to-emit-assembly-error-message"></a>Assembly wurde nicht generiert: \<Fehlermeldung >

Visual Basic-Compiler Ruft den Assemblylinker (*Al.exe*, auch bekannt als Alink) zum Generieren einer Assembly mit einem Manifest und der Linker meldet einen Fehler verwendet, in der Ausgabephase der Assemblyerstellung.

**Fehler-ID:** BC30145

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Überprüfen Sie die angegebene Fehlermeldung, und wenden Sie sich an das Thema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) für weitere erläuterungen und Hinweise zu erhalten.

2. Versuchen Sie es manuell zu signieren der Assemblys, entweder die [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) oder [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).

3. Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.

### <a name="to-sign-the-assembly-manually"></a>So signieren Sie die Assembly manuell

1. Verwenden Sie die [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) zum Erstellen einer Datei Paar aus privatem und öffentlichem Schlüssel.

   Diese Datei enthält eine *snk* Erweiterung.

2. Löschen Sie den COM-Verweis, der für den Fehler verantwortlich ist, aus Ihrem Projekt.

3. Öffnen der [Developer-Eingabeaufforderung für Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).

   Geben Sie im Windows 10, **Developer-Eingabeaufforderung** in das Suchfeld auf der Taskleiste. Wählen Sie dann **Developer-Eingabeaufforderung für Visual Studio 2017** in der Ergebnisliste aus.

4. Wechseln Sie zu dem Verzeichnis, in dem Sie den Assemblywrapper platzieren möchten.

5. Geben Sie folgenden Befehl ein:

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   Ein Beispiel der eigentliche Befehl Ihnen eingegebenen ist:

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > Verwenden Sie doppelte Anführungszeichen, wenn ein Pfad- oder Dateiname Leerzeichen enthält.

6. Fügen Sie in Visual Studio einen .NET Framework-Assembly-Verweis auf die Datei, die Sie gerade erstellt haben.

## <a name="see-also"></a>Siehe auch

- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Sn.exe (Strong Name-Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)
- [Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)