---
title: "Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile"
ms.date: 09-29-2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.build.commandline
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
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8012e310bb04ec3acef0790f9cd50ed42dd9286a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile

Die Datei VsDevCmd.bat legt die entsprechenden Umgebungsvariablen für Befehlszeilenbuilds fest. Weitere Informationen zu VsDevCmd.bat, finden Sie unter [Knowledge Base-Artikel Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).  

> [!NOTE]
> Die VsDevCmd.bat-Datei ist eine neue Datei, die mit Visual Studio 2017 übermittelt. Visual Studio 2015 und frühere Versionen VSVARS32.bat, die für den gleichen Zweck verwendet werden. Diese Datei unter \Programme\Microsoft Visual Studio gespeichert wurde\\*Version*\Common7\Tools "oder" Programme (x86) \Microsoft Visual Studio\\*Version*\Common7\Tools.
  
Wenn die aktuelle Version von Visual Studio auf einem Computer, die auch eine frühere Version von Visual Studio verfügt installiert ist, sollten Sie nicht VsDevCmd.bat und VSVARS32 ausführen. BAT aus unterschiedlichen Versionen im selben Eingabeaufforderungsfenster ein. Stattdessen sollten Sie den Befehl für jede Version in einem eigenen Fenster ausführen.
  
### <a name="to-run-vsdevcmdbat"></a>VsDevCmd.BAT ausführen  
  
1.  Aus der **starten** öffnen Sie im Menü der **Developer-Eingabeaufforderung für VS 2017**.  Es ist der **Visual Studio 2017** Ordner.
  
2.  Ändern Sie zu \Programme\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools "oder" \Programme Dateien (x86) \Microsoft Visual Studio\\ *Version*\\*Angebot*\Common7\Tools Unterverzeichnis Ihrer Installation.  (*Version* ist *2017* für die aktuelle Version. *Angebot* ist einer der *Enterprise*, *Professional* oder *Community*.)
  
3.  Führen Sie dazu VsDevCmd.bat **VsDevCmd**.  
  
    > [!CAUTION]
    >  VsDevCmd.bat kann von Computer zu Computer unterschiedlich sein. Ersetzen Sie eine fehlende oder beschädigte VsDevCmd.bat-Datei nicht durch eine VsDevCmd.bat von einem anderen Computer. Führen Sie stattdessen Setup erneut aus, um die fehlende Datei zu ersetzen.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen über die Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
