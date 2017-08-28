---
title: -debug (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /debug
dev_langs:
- CSharp
helpviewer_keywords:
- debug compiler option [C#]
- -debug compiler option [C#]
- /debug compiler option [C#]
ms.assetid: e2b48c07-01bc-45cc-a52c-92e9085eb969
caps.latest.revision: 19
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
ms.openlocfilehash: 82656c8354288dd2f7e5b0dcb2905b6c050c0521
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="debug-c-compiler-options"></a>/debug (C#-Compileroptionen)
Die Option **/debug** führt dazu, dass der Compiler Debuginformationen generiert und sie in der Ausgabedatei bzw. in Ausgabedateien platziert.  
  
## <a name="syntax"></a>Syntax  
  
```console  
/debug[+ | -]  
/debug:{full | pdbonly}  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Wenn `+` oder nur **/debug** angegeben wird, generiert der Compiler Debuginformationen und platziert sie in einer Programmdatenbank (PDB-Datei). Wenn Sie `-` angeben, was im Endeffekt dasselbe ist, wie **/debug** nicht anzugeben, werden keine Debuginformationen erstellt.  
  
 `full` &#124; `pdbonly`  
 Gibt den Typ der Debuginformationen an, die vom Compiler generiert werden. Das vollständige Argument, das aktiv ist, wenn Sie **/debug:pdbonly** nicht angeben, ermöglicht das Anfügen eines Debuggers an das ausgeführte Programm. Durch die Angabe von pdbonly wird das Debuggen von Quellcode möglich, wenn das Programm im Debugger gestartet wird. Der Assembler wird jedoch nur angezeigt, wenn das aktive Programm an den Debugger angefügt ist.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Option, um Debugbuilds zu erstellen. Wenn **/debug**, **/debug+** oder **/debug:full** nicht angegeben ist, können Sie die Ausgabedatei Ihres Programms nicht debuggen.  
  
 Wenn Sie **/debug:full** verwenden, beachten Sie, dass dies Einfluss auf die Geschwindigkeit und Größe von optimiertem JIT-Code hat und die Codequalität mit **/debug:full** etwas beeinträchtigen kann. Zum Generieren von Releasecode empfehlen wir **/debug:pdbonly** oder keine PDB-Datei.  
  
> [!NOTE]
>  Ein Unterschied zwischen **/debug:pdbonly** und **/debug:full** besteht darin, dass der Compiler mit **/debug:full** ein <xref:System.Diagnostics.DebuggableAttribute> ausgibt, was dem JIT-Compiler mitteilt, dass die Debuginformation verfügbar ist. Deshalb wird ein Fehler ausgegeben, wenn in Ihrem Code <xref:System.Diagnostics.DebuggableAttribute> auf FALSE festgelegt ist, wenn Sie **/debug:full** verwenden.  
  
 Weitere Informationen zur Konfiguration der Leistung einer Anwendung beim Debuggen finden Sie unter [Erleichtern des Debuggens für ein Image](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
 Informationen zum Ändern des Speicherorts der PDB-Datei finden Sie unter [/pdb (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Build** .  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert** .  
  
4.  Ändern Sie die Eigenschaft der **Debuginformation**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DebugSymbols%2A>.  
  
## <a name="example"></a>Beispiel  
 Platzieren Sie die Debuginformationen in der Ausgabedatei `app.pdb`:  
  
```console  
csc /debug /pdb:app.pdb test.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)   
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)

