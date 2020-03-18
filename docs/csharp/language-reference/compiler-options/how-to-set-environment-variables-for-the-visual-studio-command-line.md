---
title: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile
ms.date: 12/20/2019
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
ms.openlocfilehash: 99e2a837877494dd4c7e0106047bce3cc39a9282
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75342363"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile

Die Umgebungsvariablen, die für Befehlszeilenbuilds erforderlich sind, werden durch die Datei VSDevCmd.bat festgelegt.

> [!NOTE]
> In Visual Studio 2015 und früheren Versionen wurde für den gleichen Zweck „VSVARS32.bat“ (nicht „VsDevCmd.bat“) verwendet. Diese Datei wurde unter „\Programme\Microsoft Visual Studio\\*Version*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools“ gespeichert.

Falls die aktuelle Version von Visual Studio auf einem Computer installiert ist, der zusätzlich über eine frühere Version von Visual Studio verfügt, sollten Sie die Dateien VsDevCmd.bat und VSVARS32.BAT aus unterschiedlichen Versionen nicht im selben Eingabeaufforderungsfenster ausführen. Stattdessen sollten Sie den Befehl für jede Version in ihrem eigenen Fenster ausführen.

### <a name="to-run-vsdevcmdbat"></a>Ausführen von VsDevCmd.BAT

1. Öffnen Sie über das Menü **Start** die **Developer-Eingabeaufforderung für VS 2019**.  Die Datei befindet sich im Ordner **Visual Studio 2019**.

2. Wechseln Sie zum Unterverzeichnis „Programme\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ Ihrer Installation.  (Die *Version* lautet für die aktuelle Version *2019*. *Angebot* ist einer der Werte *Enterprise*, *Professional* oder *Community*.)

3. Führen Sie VsDevCmd.bat aus, indem Sie **VsDevCmd** eingeben.

    > [!CAUTION]
    > VsDevCmd.bat kann auf verschiedenen Computern unterschiedlich sein. Falls die Datei VsDevCmd.bat nicht vorhanden oder beschädigt ist, sollten Sie sie nicht durch die VsDevCmd.bat-Datei eines anderen Computers ersetzen. Führen Sie stattdessen Setup erneut aus, um die fehlende Datei zu ersetzen.

### <a name="available-options-for-vsdevcmdbat"></a>Verfügbare Optionen für „VsDevCmd.BAT“

Um die verfügbaren Optionen für „VsDevCmd.BAT“ anzuzeigen, führen Sie den Befehl mit der `-help`-Option aus:

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a>Weitere Informationen

- [Erstellen über die Befehlszeile mit csc.exe](./command-line-building-with-csc-exe.md)
