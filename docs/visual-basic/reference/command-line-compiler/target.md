---
title: -target
ms.date: 03/13/2018
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
ms.openlocfilehash: d186670489ada51fced67ff9adeb73b14909b664
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716687"
---
# <a name="-target-visual-basic"></a>-target (Visual Basic)

Gibt das Format der Compilerausgabe an.

## <a name="syntax"></a>Syntax

```console
-target:{exe | library | module | winexe | appcontainerexe | winmdobj}
```

## <a name="remarks"></a>Hinweise

In der folgenden Tabelle werden die Auswirkungen der Option `-target` zusammengefasst:

|**Option**|**Behavior class (Behavior-Klasse)**|
|----------------|------------------|
|`-target:exe`|Bewirkt, dass der Compiler eine ausführbare Konsolenanwendung erstellt.<br /><br /> Dabei handelt es sich um die Standardoption, wenn keine `-target`-Option angegeben wurde. Die ausführbare Datei wird mit der Dateiendung „.exe“ erstellt.<br /><br /> Sofern es nicht anders mit der Option `-out` angegeben wurde, erhält die Ausgabedatei den Namen der Eingabedatei, die die `Sub Main`-Prozedur enthält.<br /><br /> Nur eine `Sub Main`-Prozedur wird in den Quellcodedateien benötigt, die in eine EXE-Datei kompiliert werden. Verwenden Sie die `-main`-Compileroption, um anzugeben, welche Klasse die `Sub Main`-Prozedur enthält.|
|`-target:library`|Bewirkt, dass der Compiler eine Dynamic Link Library (DLL-Datei) erstellt.<br /><br /> Die Dynamic Link Library-Datei wird mit der Erweiterung „.dll“ erstellt.<br /><br /> Sofern es nicht anders mit der Option `-out` angegeben wurde, erhält die Ausgabedatei den Namen der ersten Eingabedatei.<br /><br /> Beim Generieren einer DLL-Datei ist keine `Sub Main`-Prozedur erforderlich.|
|`-target:module`|Bewirkt, dass der Compiler ein Modul generiert, das einer Assembly hinzugefügt werden kann.<br /><br /> Die Ausgabedatei wird mit der Erweiterung „.netmodule“ erstellt.<br /><br /> Der .NET-CLR (Common Language Runtime) kann keine Datei laden, die keine Assembly enthält. Sie können eine solche Datei jedoch mit `-reference` in das Assemblymanifest einer Assembly einbinden.<br /><br /> Wenn der Code in einem Modul auf interne Typen in einem anderen Modul verweist, müssen beide Module mithilfe von `-reference` in ein Assemblymanifest aufgenommen werden.<br /><br /> Die Option [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) importiert Metadaten aus einem Modul.|
|`-target:winexe`|Bewirkt, dass der Compiler eine ausführbare Windows-basierte Anwendung erstellt.<br /><br /> Die ausführbare Datei wird mit der Dateiendung „.exe“ erstellt. Eine Windows-basierte Anwendung stellt eine Benutzeroberfläche über die .NET Framework-Bibliothek oder die Windows-APIs bereit.<br /><br /> Sofern es nicht anders mit der Option `-out` angegeben wurde, erhält die Ausgabedatei den Namen der Eingabedatei, die die `Sub Main`-Prozedur enthält.<br /><br /> Nur eine `Sub Main`-Prozedur wird in den Quellcodedateien benötigt, die in eine EXE-Datei kompiliert werden. Verwenden Sie in Fällen, in denen Ihr Code mehr als eine Klasse mit einer `Sub Main`-Prozedur aufweist, die `-main`-Compileroption, um anzugeben, welche Klasse die `Sub Main`-Prozedur enthält.|
|`-target:appcontainerexe`|Bewirkt, dass der Compiler eine ausführbare Windows-basierte Anwendung erstellt, die in einem App-Container ausgeführt werden muss. Diese Einstellung ist für die Verwendung in Windows 8.x Store-Anwendungen konzipiert.<br /><br /> Mit der **appcontainerexe**-Einstellung wird ein Bit im Eigenschaftenfeld der [portierbaren ausführbaren Datei](/windows/desktop/Debug/pe-format) festgelegt. Dieses Bit gibt an, dass die App in einem App-Container ausgeführt werden muss. Wenn dieses Bit festgelegt ist, tritt ein Fehler auf, wenn die `CreateProcess`-Methode versucht, die Anwendung außerhalb eines App-Containers zu starten. Abgesehen von dieser Biteinstellung entspricht **-target:appcontainerexe** der Angabe **-target:winexe**.<br /><br /> Die ausführbare Datei wird mit der Dateiendung „.exe“ erstellt.<br /><br /> Sofern Sie nicht anderweitig mithilfe der `-out`-Option angeben, wird der Name der Eingabedatei, die die `Sub Main`-Prozedur enthält, als Name für die Ausgabedatei verwendet.<br /><br /> Nur eine `Sub Main`-Prozedur wird in den Quellcodedateien benötigt, die in eine EXE-Datei kompiliert werden. Wenn Ihr Code mehr als eine Klasse mit einer `Sub Main`-Prozedur aufweist, sollten Sie die `-main`-Compileroption verwenden, um anzugeben, welche Klasse die `Sub Main`-Prozedur enthält.|
|`-target:winmdobj`|Bewirkt, dass der Compiler eine temporäre Datei erstellt, die Sie in eine Windows-Runtime-Binärdatei (.winmd) konvertieren können. Die WINMD-Datei kann von verwalteten Sprachprogrammen und von JavaScript- und C++-Programmen verwendet werden.<br /><br /> Die temporäre Datei wird mit der Erweiterung „.winmdobj“ erstellt.<br /><br /> Sofern Sie nicht anderweitig mithilfe der `-out`-Option angeben, erhält die Ausgabedatei den Namen der ersten Eingabedatei. Eine `Sub Main`-Prozedur ist nicht erforderlich.<br /><br /> Die WINMDOBJ-Datei ist so konzipiert, dass sie als Eingabe für das <xref:Microsoft.Build.Tasks.WinMDExp>-Exporttool verwendet werden kann, um eine Windows-Metadatendatei (WINMD-Datei) zu erzeugen. Die WINMD-Datei hat die Erweiterung „.winmd“ und enthält sowohl den Code aus der ursprünglichen Bibliothek als auch die WINMD-Definitionen für JavaScript, C++ und die Windows-Runtime.|

Wenn Sie `-target:module` nicht angegeben haben, wird durch `-target` ein .NET Framework-Assemblymanifest zu einer Ausgabedatei hinzugefügt.

Jede Instanz von „Vbc.exe“ erzeugt höchstens eine Ausgabedatei. Wenn Sie eine Compileroption wie `-out` oder `-target` mehrmals angeben, gilt diejenige, die zuletzt vom Compiler verarbeitet wird. Informationen zu allen Dateien in einer Kompilierung werden dem Manifest hinzugefügt. Alle Ausgabedateien außer denen, die mit `-target:module` erstellt wurden, enthalten Assemblymetadaten im Manifest. Verwenden Sie [„Ildasm.exe“ (IL Disassembler)](../../../framework/tools/ildasm-exe-il-disassembler.md), um die Metadaten in einer Ausgabedatei anzuzeigen.

Die Kurzform von `-target` ist `-t`.

### <a name="to-set--target-in-the-visual-studio-ide"></a>Festlegen von -target in der Visual Studio-IDE

1. Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.

2. Klicken Sie auf die Registerkarte **Anwendung** .

3. Ändern Sie den Wert im Feld **Anwendungstyp**.

## <a name="example"></a>Beispiel

Der folgende Code kompiliert `in.vb`, wobei `in.dll` erstellt wird:

```console
vbc -target:library in.vb
```

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [-reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)
- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
