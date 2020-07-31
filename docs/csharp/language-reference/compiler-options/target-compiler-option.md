---
title: -target (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /target
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
ms.openlocfilehash: 80cec001b27000e71b74f380a0f33e30602c01af
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86473908"
---
# <a name="-target-c-compiler-options"></a>-target (C#-Compileroptionen)
Die Compileroption **-target** kann in einem der folgenden Formate angegeben werden:  
  
 [/target:appcontainerexe](./target-appcontainerexe-compiler-option.md)  
 So erstellen Sie eine EXE-Datei für Windows 8.x Store-Apps.  
  
 [/target:exe](./target-exe-compiler-option.md)  
 So erstellen Sie eine EXE-Datei.  
  
 [/target:library](./target-library-compiler-option.md)  
 So erstellen Sie eine Codebibliothek.  
  
 [/target:module](./target-module-compiler-option.md)  
 So erstellen Sie ein Modul.  
  
 [/target:winexe](./target-winexe-compiler-option.md)  
 So erstellen Sie ein Windows-Programm.  
  
 [/target:winmdobj](./target-winmdobj-compiler-option.md)  
 So erstellen Sie eine WINMDOBJ-Zwischendatei.  
  
 Wenn Sie **-target:module** nicht angegeben haben, verursacht **-target**, dass ein .NET Framework-Assemblymanifest in einer Ausgabedatei platziert wird. Weitere Informationen finden Sie unter [Assemblys in .NET](../../../standard/assembly/index.md) und [Häufig verwendete Attribute](../attributes/global.md).  
  
 Das Assemblymanifest wird in der ersten EXE-Ausgabedatei in der Kompilierung oder in der ersten DLL platziert, falls es keine EXE-Ausgabedatei gibt. In der folgenden Befehlszeile wird das Manifest z.B. in `1.exe` platziert:  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 Der Compiler erstellt nur ein Assemblymanifest pro Kompilierung. Informationen über alle Dateien in einer Kompilierung werden im Assemblymanifest platziert. Alle Ausgabedateien außer denen, die mit **-target:module** erstellt wurden, können ein Assemblymanifest enthalten. Wenn mehrere Ausgabedateien in der Befehlszeile erstellt werden, kann nur ein Assemblymanifest erstellt werden, und es muss in die erste Ausgabedatei gehen, die in der Befehlszeile angegeben wurde. Unabhängig von der ersten Ausgabedatei ( **-target:exe**, **-target:winexe**, **-target:library** oder **-target:module**) müssen alle anderen Ausgabedateien, die in der selben Kompilierung erzeugt wurden, Module sein ( **-target:module**).  
  
 Wenn Sie eine Assembly erstellen, können Sie angeben, dass der ganze oder ein Teil des Codes mit dem <xref:System.CLSCompliantAttribute>-Attribut CLS-kompatibel ist.  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
- [-subsystemversion (C#-Compileroptionen)](./subsystemversion-compiler-option.md)
