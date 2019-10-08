---
title: -Target (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
ms.openlocfilehash: 2d7ccfc6b033a9021e683a4a2501ca2ccc29956d
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004935"
---
# <a name="-target-visual-basic"></a>-Target (Visual Basic)
Gibt das Format der Compilerausgabe an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle werden die Auswirkungen der `-target`-Option zusammengefasst.  
  
|**Option**|**Behavior class (Behavior-Klasse)**|  
|----------------|------------------|  
|`-target:exe`|Bewirkt, dass der Compiler eine ausführbare Konsolenanwendung erstellt.<br /><br /> Dies ist die Standardoption, wenn keine `-target`-Option angegeben wird. Die ausführbare Datei wird mit der Erweiterung ". exe" erstellt.<br /><br /> Sofern nicht anders mit der Option "`/out`" angegeben, nimmt der Name der Ausgabedatei den Namen der Eingabedatei an, die die `Sub Main`-Prozedur enthält.<br /><br /> In den Quell Code Dateien, die in eine exe-Datei kompiliert werden, ist nur eine `Sub Main`-Prozedur erforderlich. Verwenden Sie die `-main`-Compileroption, um anzugeben, welche Klasse die `Sub Main`-Prozedur enthält.|  
|`-target:library`|Bewirkt, dass der Compiler eine Dynamic Link Library (dll) erstellt.<br /><br /> Die Dynamic Link Library-Datei wird mit der Erweiterung ". dll" erstellt.<br /><br /> Sofern nicht anders mit der Option "`-out`" angegeben, nimmt der Name der Ausgabedatei den Namen der ersten Eingabedatei.<br /><br /> Beim Aufbau einer dll ist eine `Sub Main`-Prozedur nicht erforderlich.|  
|`-target:module`|Bewirkt, dass der Compiler ein Modul generiert, das einer Assembly hinzugefügt werden kann.<br /><br /> Die Ausgabedatei wird mit der Erweiterung ". netmodule" erstellt.<br /><br /> Der .NET-Common Language Runtime kann keine Datei laden, die keine Assembly enthält. Sie können eine solche Datei jedoch mit `-reference` in das Assemblymanifest einer Assembly einbinden.<br /><br /> Wenn Code in einem Modul auf interne Typen in einem anderen Modul verweist, müssen beide Module mithilfe von `-reference` in ein Assemblymanifest eingebunden werden.<br /><br /> Die Option [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) importiert Metadaten aus einem Modul.|  
|`-target:winexe`|Bewirkt, dass der Compiler eine ausführbare Windows-basierte Anwendung erstellt.<br /><br /> Die ausführbare Datei wird mit der Erweiterung ". exe" erstellt. Eine Windows-basierte Anwendung ist eine, die eine Benutzeroberfläche entweder aus der .NET Framework-Klassenbibliothek oder mit den Windows-APIs bereitstellt.<br /><br /> Sofern nicht anders mit der Option "`-out`" angegeben, nimmt der Name der Ausgabedatei den Namen der Eingabedatei an, die die `Sub Main`-Prozedur enthält.<br /><br /> In den Quell Code Dateien, die in eine exe-Datei kompiliert werden, ist nur eine `Sub Main`-Prozedur erforderlich. Verwenden Sie in Fällen, in denen Ihr Code mehr als eine Klasse mit einer `Sub Main`-Prozedur aufweist, die `-main`-Compileroption, um anzugeben, welche Klasse die `Sub Main`-Prozedur enthält.|  
|`-target:appcontainerexe`|Bewirkt, dass der Compiler eine ausführbare Windows-basierte Anwendung erstellt, die in einem App-Container ausgeführt werden muss. Diese Einstellung ist für die Verwendung für [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)]-Anwendungen vorgesehen.<br /><br /> Mit der Einstellung " **appcontainerexe** " wird ein Bit im Feld "Merkmale" der [portablen ausführbaren](/windows/desktop/Debug/pe-format) Datei festgelegt. Dieses Bit gibt an, dass die app in einem App-Container ausgeführt werden muss. Wenn dieses Bit festgelegt ist, tritt ein Fehler auf, wenn die `CreateProcess`-Methode versucht, die Anwendung außerhalb eines App-Containers zu starten. Abgesehen von dieser Biteinstellung entspricht **-target: appcontainerexe** dem **-target: winexe**.<br /><br /> Die ausführbare Datei wird mit der Erweiterung ". exe" erstellt.<br /><br /> Wenn Sie nicht anders angeben, indem Sie die Option `-out` verwenden, wird der Name der Eingabedatei, die die `Sub Main`-Prozedur enthält, als Ausgabe Dateiname verwendet.<br /><br /> In den Quell Code Dateien, die in eine exe-Datei kompiliert werden, ist nur eine `Sub Main`-Prozedur erforderlich. Wenn Ihr Code mehr als eine Klasse enthält, die über eine `Sub Main`-Prozedur verfügt, verwenden Sie die `-main`-Compileroption, um anzugeben, welche Klasse die `Sub Main`-Prozedur enthält.|  
|`-target:winmdobj`|Bewirkt, dass der Compiler eine zwischen Datei erstellt, die Sie in eine Windows-Runtime binäre Datei (. winmd) konvertieren können. Die winmd-Datei kann neben den Programmen für verwaltete C++ Sprache auch von JavaScript und Programmen verwendet werden.<br /><br /> Die zwischen Datei wird mit der Erweiterung ". winmdobj" erstellt.<br /><br /> Wenn Sie nicht anders angeben, indem Sie die Option `-out` verwenden, wird der Name der ersten Eingabedatei als Name der Ausgabedatei verwendet. Eine `Sub Main`-Prozedur ist nicht erforderlich.<br /><br /> Die winmdobj-Datei ist so konzipiert, dass Sie als Eingabe für das <xref:Microsoft.Build.Tasks.WinMDExp>-Export Tool verwendet wird, um eine Windows-Metadatendatei (winmd) zu entwickeln. Die winmd-Datei hat die Erweiterung ". winmd" und enthält sowohl den Code aus der ursprünglichen Bibliothek als auch die winmd C++-Definitionen, die von JavaScript, und den Windows-Runtime verwendet werden.|  
  
 Wenn Sie nicht `-target:module` angeben, bewirkt `-target`, dass einer Ausgabedatei ein .NET Framework Assemblymanifest hinzugefügt wird.  
  
 Jede Instanz von "Vbc. exe" erzeugt höchstens eine Ausgabedatei. Wenn Sie eine Compileroption angeben, z. b. `-out` oder `-target` mehr als einmal, wird der letzte, der vom Compiler verarbeitet wird, in Kraft gesetzt. Informationen zu allen Dateien in einer Kompilierung werden dem Manifest hinzugefügt. Alle Ausgabedateien, mit Ausnahme derjenigen, die mit `-target:module` erstellt wurden, enthalten Assemblymetadaten im Manifest. Verwenden Sie [Ildasm. exe (IL-Disassembler)](../../../framework/tools/ildasm-exe-il-disassembler.md) , um die Metadaten in einer Ausgabedatei anzuzeigen.  
  
 Die Kurzform von `-target` ist `-t`.  
  
### <a name="to-set--target-in-the-visual-studio-ide"></a>So legen Sie "-target" in der Visual Studio-IDE fest  
  
1. Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.   
  
2. Klicken Sie auf die Registerkarte **Anwendung** .  
  
3. Ändern Sie den Wert im Feld **Anwendungstyp** .  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird `in.vb` kompiliert und `in.dll` erstellt:  
  
```console
vbc -target:library in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-Out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [-Verweis (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)
- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
