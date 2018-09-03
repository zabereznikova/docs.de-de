---
title: 'Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile'
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
ms.openlocfilehash: 77375e428fe0563c0b533ca97abd21070e850682
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43466737"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile

Die Umgebungsvariablen, die für Befehlszeilenbuilds erforderlich sind, werden durch die Datei VSDevCmd.bat festgelegt. Weitere Informationen zu VsDevCmd.bat finden Sie im [Knowledge Base-Artikel Q248802](https://support.microsoft.com/help/248802/you-receive-the-out-of-environment-space-error-message-when-you-execut).  

> [!NOTE]
> Bei der Datei VsDevCmd.bat handelt es sich um eine neue Datei, die im Lieferumfang von Visual Studio 2017 enthalten ist. In Visual Studio 2015 und früheren Versionen wurde für den gleichen Zweck VSVARS32.bat verwendet. Diese Datei wurde unter „\Programme\Microsoft Visual Studio\\*Version*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools“ gespeichert.
  
Falls die aktuelle Version von Visual Studio auf einem Computer installiert ist, der zusätzlich über eine frühere Version von Visual Studio verfügt, sollten Sie die Dateien VsDevCmd.bat und VSVARS32.BAT aus unterschiedlichen Versionen nicht im selben Eingabeaufforderungsfenster ausführen. Stattdessen sollten Sie den Befehl für jede Version in ihrem eigenen Fenster ausführen.
  
### <a name="to-run-vsdevcmdbat"></a>Ausführen von VsDevCmd.BAT  
  
1.  Öffnen Sie über das Menü **Start** die **Developer-Eingabeaufforderung für VS 2017**.  Sie befindet sich im Ordner **Visual Studio 2017**.
  
2.  Wechseln Sie zum Unterverzeichnis „Programme\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ Ihrer Installation.  (Die *Version* lautet für die aktuelle Version *2017*. *Angebot* ist einer der Werte *Enterprise*, *Professional* oder *Community*.)
  
3.  Führen Sie VsDevCmd.bat aus, indem Sie **VsDevCmd** eingeben.  
  
    > [!CAUTION]
    >  VsDevCmd.bat kann auf verschiedenen Computern unterschiedlich sein. Falls die Datei VsDevCmd.bat nicht vorhanden oder beschädigt ist, sollten Sie sie nicht durch die VsDevCmd.bat-Datei eines anderen Computers ersetzen. Führen Sie stattdessen Setup erneut aus, um die fehlende Datei zu ersetzen.  
  
## <a name="see-also"></a>Siehe auch  

- [Erstellen über die Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
