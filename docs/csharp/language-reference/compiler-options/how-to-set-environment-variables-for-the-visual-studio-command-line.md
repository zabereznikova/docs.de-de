---
title: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile
ms.date: 09/29/2017
f1_keywords:
- cs.build.commandline
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
ms.openlocfilehash: 3b69a92d28663bbbd34245435a69aea80d20fdc9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73972832"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile

Die Umgebungsvariablen, die für Befehlszeilenbuilds erforderlich sind, werden durch die Datei VSDevCmd.bat festgelegt.

> [!NOTE]
> Bei der Datei VsDevCmd.bat handelt es sich um eine neue Datei, die im Lieferumfang von Visual Studio 2017 enthalten ist. In Visual Studio 2015 und früheren Versionen wurde für den gleichen Zweck VSVARS32.bat verwendet. Diese Datei wurde unter „\Programme\Microsoft Visual Studio\\*Version*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools“ gespeichert.

Falls die aktuelle Version von Visual Studio auf einem Computer installiert ist, der zusätzlich über eine frühere Version von Visual Studio verfügt, sollten Sie die Dateien VsDevCmd.bat und VSVARS32.BAT aus unterschiedlichen Versionen nicht im selben Eingabeaufforderungsfenster ausführen. Stattdessen sollten Sie den Befehl für jede Version in ihrem eigenen Fenster ausführen.

### <a name="to-run-vsdevcmdbat"></a>Ausführen von VsDevCmd.BAT

1. Öffnen Sie über das Menü **Start** die **Developer-Eingabeaufforderung für VS 2017**.  Sie befindet sich im Ordner **Visual Studio 2017**.

2. Wechseln Sie zum Unterverzeichnis „Programme\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ Ihrer Installation.  (Die *Version* lautet für die aktuelle Version *2017*. *Angebot* ist einer der Werte *Enterprise*, *Professional* oder *Community*.)

3. Führen Sie VsDevCmd.bat aus, indem Sie **VsDevCmd** eingeben.

    > [!CAUTION]
    > VsDevCmd.bat kann auf verschiedenen Computern unterschiedlich sein. Falls die Datei VsDevCmd.bat nicht vorhanden oder beschädigt ist, sollten Sie sie nicht durch die VsDevCmd.bat-Datei eines anderen Computers ersetzen. Führen Sie stattdessen Setup erneut aus, um die fehlende Datei zu ersetzen.

### <a name="available-options-for-vsdevcmdbat"></a>Verfügbare Optionen für „VsDevCmd.BAT“

Um die verfügbaren Optionen für „VsDevCmd.BAT“ anzuzeigen, führen Sie den Befehl mit der `-help`-Option aus:

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a>Siehe auch

- [Erstellen über die Befehlszeile mit csc.exe](./command-line-building-with-csc-exe.md)
