---
title: -debug (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /debug
helpviewer_keywords:
- debug compiler option [C#]
- -debug compiler option [C#]
- /debug compiler option [C#]
ms.assetid: e2b48c07-01bc-45cc-a52c-92e9085eb969
ms.openlocfilehash: 8bb2b411dc867b6a43e52058dccf2ac980cf0b1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69922513"
---
# <a name="-debug-c-compiler-options"></a>-debug (C#-Compileroptionen)
Die Option **-debug** führt dazu, dass der Compiler Debuginformationen generiert und sie in der Ausgabedatei bzw. in Ausgabedateien platziert.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-debug[+ | -]  
-debug:{full | pdbonly}  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Wenn `+` oder nur **-debug** angegeben wird, generiert der Compiler Debuginformationen und platziert sie in einer Programmdatenbank (PDB-Datei). Wenn Sie `-` angeben (entspricht dem Weglassen von **-debug**), werden keine Debuginformationen erstellt.  
  
 `full` &#124; `pdbonly`  
 Gibt den Typ der Debuginformationen an, die vom Compiler generiert werden. Das vollständige Argument, das aktiv ist, wenn Sie **-debug:pdbonly** nicht angeben, ermöglicht das Anfügen eines Debuggers an das ausgeführte Programm. Durch die Angabe von pdbonly wird das Debuggen von Quellcode möglich, wenn das Programm im Debugger gestartet wird. Der Assembler wird jedoch nur angezeigt, wenn das aktive Programm an den Debugger angefügt ist.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Option, um Debugbuilds zu erstellen. Wenn **-debug**, **-debug+** oder **-debug:full** nicht angegeben ist, können Sie die Ausgabedatei Ihres Programms nicht debuggen.  
  
 Wenn Sie **-debug:full** verwenden, beachten Sie, dass dies Einfluss auf die Geschwindigkeit und Größe von optimiertem JIT-Code hat und die Codequalität mit **-debug:full** beeinträchtigt sein kann. Zum Generieren von Releasecode wird empfohlen, **-debug:pdbonly** oder keine PDB-Datei zu verwenden.  
  
> [!NOTE]
> Ein Unterschied zwischen **-debug:pdbonly** und **-debug:full** besteht darin, dass der Compiler mit **-debug:full** ein <xref:System.Diagnostics.DebuggableAttribute>-Objekt ausgibt, das dem JIT-Compiler mitteilt, dass die Debuginformation verfügbar ist. Deshalb wird ein Fehler ausgegeben, wenn bei der Verwendung von **-debug:full**<xref:System.Diagnostics.DebuggableAttribute> in Ihrem Code auf FALSE festgelegt ist.  
  
 Weitere Informationen zur Konfiguration der Leistung einer Anwendung beim Debuggen finden Sie unter [Erleichtern des Debuggens für ein Image](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
 Informationen zum Ändern des Speicherorts der PDB-Datei finden Sie unter [-pdb (C#-Compileroptionen)](./pdb-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2. Klicken Sie auf die Eigenschaftenseite **Build** .  
  
3. Klicken Sie auf die Schaltfläche **Erweitert** .  
  
4. Ändern Sie die Eigenschaft der **Debuginformation**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DebugSymbols%2A>.  
  
## <a name="example"></a>Beispiel  
 Platzieren Sie die Debuginformationen in der Ausgabedatei `app.pdb`:  
  
```console  
csc -debug -pdb:app.pdb test.cs  
```  
  
## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
