---
title: "Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.build.commandline
dev_langs:
- CSharp
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
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 569683169c6d7ae50c33ed06d3b365a663f16715
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a>Gewusst wie: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile
Die Umgebungsvariablen, die für Befehlszeilenbuilds erforderlich sind, werden durch die Datei VSVARS32.BAT festgelegt. Weitere Informationen zu „vsvars32.bat“ finden Sie im [Knowledge Base-Artikel Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).  
  
 Falls die aktuelle Version von Visual Studio auf einem Computer installiert ist, der zusätzlich über eine frühere Version von Visual Studio verfügt, sollten Sie die Dateien VSVARS32.BAT und VCVARS32.BAT nicht aus unterschiedlichen Versionen im selben Eingabeaufforderungsfenster ausführen.  
  
### <a name="to-run-vsvars32bat"></a>So führen Sie VSVARS32.BAT aus  
  
1.  Öffnen Sie über das Menü **Start** die **Developer-Eingabeaufforderung für VS2012**.  
  
2.  Wechseln Sie zum Unterverzeichnis „Programme\Microsoft Visual Studio *Version*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio *Version*\Common7\Tools“ Ihrer Installation.  
  
3.  Führen Sie „VSVARS32.BAT“ aus, indem Sie **VSVARS32** eingeben.  
  
    > [!CAUTION]
    >  VSVARS32.BAT kann auf verschiedenen Computern unterschiedlich sein. Falls die Datei VSVARS32.BAT nicht vorhanden oder beschädigt ist, sollten Sie sie nicht durch die VSVARS32.BAT-Datei eines anderen Computers ersetzen. Führen Sie stattdessen Setup erneut aus, um die fehlende Datei zu ersetzen.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen über die Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)

