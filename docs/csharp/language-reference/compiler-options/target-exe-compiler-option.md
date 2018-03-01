---
title: -target:exe (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /exe
helpviewer_keywords:
- target compiler options [C#], /target:exe
- /target compiler options [C#], /target:exe
- -target compiler options [C#], /target:exe
ms.assetid: bda5717d-1b91-4848-956b-fcf85c30e432
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 515359b7a8a76e20896389b308df34db03f3798d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-targetexe-c-compiler-options"></a>-target:exe (C#-Compileroptionen)
Die Option **-target:exe** bewirkt, dass der Compiler eine ausführbare Konsolenanwendung (EXE) erstellt.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-target:exe  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Option **-target:exe** ist standardmäßig aktiviert. Die ausführbare Datei wird mit der Dateiendung „.exe“ erstellt.  
  
 Verwenden Sie [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), um ein ausführbares Windows-Programm zu erstellen.  
  
 Sofern Sie nicht die Option [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) verwenden, erhält die Ausgabedatei den Namen der Eingabedatei, die die [Main](../../../csharp/programming-guide/main-and-command-args/index.md)-Methode enthält.  
  
 Wenn es in der Befehlszeile angegeben wurde, werden alle Dateien bis zur nächsten Option **-out** oder **-target:module** verwendet, um die EXE-Datei zu erstellen.  
  
 Nur eine **Main**-Methode wird in den Quellcodedateien benötigt, die in eine EXE-Datei kompiliert werden. Sollte Ihr Code mehr als eine Klasse mit einer **Main**-Methode haben, können Sie mit der Compileroption [-main](../../../csharp/language-reference/compiler-options/main-compiler-option.md) angeben, welche Klasse die Methode **Main** enthält.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Anwendung**.  
  
3.  Ändern Sie die Eigenschaft **Ausgabetyp**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Beispiel  
 Jede der folgenden Befehlszeilen wird `in.cs` kompilieren, wodurch `in.exe` erstellt wird:  
  
```console  
csc -target:exe in.cs  
csc in.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [-target (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)
