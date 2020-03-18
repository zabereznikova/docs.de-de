---
title: -out (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /out
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
ms.openlocfilehash: 6c8408c0c613e361dae0c1db19f854e9421ca467
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970378"
---
# <a name="-out-c-compiler-options"></a>-out (C#-Compileroptionen)
Die Option **-out** gibt den Namen der Ausgabedatei an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Der Name der Ausgabedatei, die vom Compiler erstellt wurde  
  
## <a name="remarks"></a>Hinweise  
 In der Befehlszeile ist es möglich, mehrere Ausgabedateien für die Kompilierung anzugeben. Der Compiler geht davon aus, mindestens eine Quellcodedatei nach der Option **-out** zu finden. Anschließend werden alle Quellcodedateien in der von der Option **-out** angegebenen Ausgabedatei kompiliert.  
  
 Geben Sie den vollständigen Namen und die Erweiterung der Datei an, die Sie erstellen möchten.  
  
 Wenn Sie den Namen der Ausgabedatei nicht angeben:  
  
- Übernimmt eine EXE-Datei den Namen aus der Quellcodedatei, die die **Main**-Methode enthält.  
  
- Eine DLL- oder NETMODULE-Datei übernimmt den Namen aus der ersten Quellcodedatei.  
  
 Eine Quellcodedatei zum Kompilieren einer Ausgabedatei kann nicht in der gleichen Kompilierung für die Kompilierung einer anderen Ausgabedatei verwendet werden.  
  
 Wenn bei einer Befehlszeilenkompilierung mehrere Ausgabedateien erstellt werden, sollten Sie bedenken, dass nur eine der Ausgabedateien eine Assembly sein kann und dass nur die erste angegebene Ausgabedatei (implizit oder explizit mit **-out**) die Assembly sein kann.  
  
 Alle Module, die als Teil einer Kompilierung erstellt werden, werden Dateien, die jeder Assembly zugeordnet sind, die auch bei der Kompilierung erstellt werden. Verwenden Sie [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md), um das Assemblymanifest mit den zugehörigen Dateien anzuzeigen.  
  
 Die Compileroption „-out“ ist erforderlich, damit eine EXE-Datei das Ziel einer Friend-Assembly sein kann. Weitere Informationen finden Sie unter [Friend-Assemblys](../../../standard/assembly/friend.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2. Klicken Sie auf die Eigenschaftenseite **Anwendung**.  
  
3. Ändern Sie die Eigenschaft **Assemblyname**.  
  
     So legen Sie diese Compileroption programmgesteuert fest: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> ist eine schreibgeschützte Eigenschaft, die durch eine Kombination aus dem Projekttyp (ausführbare Datei, Bibliothek usw.) und dem Namen der Assembly bestimmt wird. Das Ändern von einer oder diesen beiden Eigenschaften ist erforderlich, um den Namen der Ausgabedatei festzulegen.  
  
## <a name="example"></a>Beispiel  
 Kompilieren Sie `t.cs`, und erstellen Sie die Ausgabedatei `t.exe` und die Datei `t2.cs` sowie die Modulausgabedatei `mymodule.netmodule`:  
  
```console  
csc t.cs -out:mymodule.netmodule -target:module t2.cs  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Friend-Assemblys](../../../standard/assembly/friend.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
