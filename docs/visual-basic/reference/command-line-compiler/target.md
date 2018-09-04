---
title: -Target (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17528bb9faf137029b35e4a9f28bab7a28ae25db
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43542257"
---
# <a name="-target-visual-basic"></a>-Target (Visual Basic)
Gibt das Format der Ausgabe des Compilers.  
  
## <a name="syntax"></a>Syntax  
  
```  
-target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## <a name="remarks"></a>Hinweise  
 Der folgenden Tabelle werden die Auswirkungen der `-target` Option.  
  
|**Option**|**Verhalten**|  
|----------------|------------------|  
|`-target:exe`|Bewirkt, dass der Compiler eine ausführbare Konsolenanwendung zu erstellen.<br /><br /> Dies ist die Standardoption, wenn kein `-target` angegeben wird. Die ausführbare Datei wird mit der Erweiterung .exe erstellt.<br /><br /> Sofern nicht anders angegeben mit der `/out` Option den Namen der Ausgabedatei erhält den Namen der Eingabedatei, die enthält die `Sub Main` Verfahren.<br /><br /> Nur ein `Sub Main` Prozedur ist erforderlich. in den Quellcodedateien, die in eine .exe-Datei kompiliert werden. Verwenden der `-main` Compileroption, um anzugeben, welche Klasse enthält die `Sub Main` Verfahren.|  
|`-target:library`|Bewirkt, dass den Compiler eine Dynamic Link Library (DLL) erstellt.<br /><br /> Die Dynamic Link Library-Datei wird mit der Erweiterung ".dll" erstellt.<br /><br /> Sofern nicht anders angegeben mit der `-out` Option den Namen der Ausgabedatei erhält den Namen der ersten Eingabedatei.<br /><br /> Beim Erstellen einer DLL ein `Sub Main` Verfahren ist nicht erforderlich.|  
|`-target:module`|Veranlasst den Compiler an, um ein Modul zu generieren, die auf eine Assembly hinzugefügt werden können.<br /><br /> Die Ausgabedatei wird mit der Erweiterung NETMODULE-Datei erstellt.<br /><br /> Die keine Assembly besitzt eine Datei kann von die .NET common Language Runtime kann nicht geladen werden. Sie können jedoch eine solche Datei in das Assemblymanifest einer Assembly integrieren, mithilfe von `-reference`.<br /><br /> Wenn Code in einem Modul auf interne Typen in einem anderen Modul verweist, müssen beide Module in ein Assemblymanifest integriert werden, indem `-reference`.<br /><br /> Die [- Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) Option importiert Metadaten aus einem Modul.|  
|`-target:winexe`|Bewirkt, dass den Compiler eine ausführbare Windows-basierte Anwendung erstellt.<br /><br /> Die ausführbare Datei wird mit der Erweiterung .exe erstellt. Eine Windows-basierten Anwendung ist eine, die eine Benutzeroberfläche entweder bietet die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Class-Bibliothek oder den Win32-APIs.<br /><br /> Sofern nicht anders angegeben mit der `-out` Option den Namen der Ausgabedatei erhält den Namen der Eingabedatei, die enthält die `Sub Main` Verfahren.<br /><br /> Nur ein `Sub Main` Prozedur ist erforderlich. in den Quellcodedateien, die in eine .exe-Datei kompiliert werden. In Fällen, in denen Ihr Code mehr als eine Klasse, die eine `Sub Main` Verfahren verwenden die `-main` Compileroption, um anzugeben, welche Klasse enthält die `Sub Main` Prozedur|  
|`-target:appcontainerexe`|Bewirkt, dass der Compiler eine ausführbare Windows-basierte Anwendung erstellen, die in einem app-Container ausgeführt werden muss. Diese Einstellung dient für zu verwendende [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] Anwendungen.<br /><br /> Die **Appcontainerexe** Einstellung legt ein bit im Feld "Eigenschaften" des der [Portable Executable](/windows/desktop/Debug/pe-format) Datei. Dieses Bit gibt an, dass die app in einem app-Container ausgeführt werden muss. Wenn dieses Bit festgelegt ist, tritt ein Fehler auf, wenn die `CreateProcess` Methode versucht, die die Anwendung außerhalb von einem app-Container zu starten. Dieses bit festgelegt ist abgesehen von **--target: Appcontainerexe** entspricht **--target: Winexe**.<br /><br /> Die ausführbare Datei wird mit der Erweiterung .exe erstellt.<br /><br /> Es sei denn, Sie geben Sie andernfalls mit der `-out` Option den Namen der Ausgabedatei erhält den Namen der Eingabedatei, die enthält die `Sub Main` Prozedur.<br /><br /> Nur ein `Sub Main` Prozedur ist erforderlich. in den Quellcodedateien, die in eine .exe-Datei kompiliert werden. Wenn Ihr Code mehr als eine Klasse enthält, besitzt eine `Sub Main` Verfahren verwenden die `-main` Compileroption, um anzugeben, welche Klasse enthält die `Sub Main` Prozedur|  
|`-target:winmdobj`|Bewirkt, dass den Compiler eine Zwischendatei erstellt, die Sie in einer Windows-Runtime-Binärdatei (.winmd) konvertieren können. Die winmd-Datei kann von JavaScript und C++-Programmen verwalteten Sprachprogrammen genutzt werden.<br /><br /> Die Zwischendatei wird mit der Erweiterung winmdobj erstellt.<br /><br /> Es sei denn, die andernfalls geben Sie über die `-out` Option den Namen der Ausgabedatei erhält den Namen der ersten Eingabedatei. Ein `Sub Main` Verfahren ist nicht erforderlich.<br /><br /> Die winmdobj-Datei dient als Eingabe für werden die <xref:Microsoft.Build.Tasks.WinMDExp> export-Tool aus, um eine Windows-Metadatendatei (WinMD) erzeugt. Die WinMD-Datei verfügt über eine winmd-Erweiterung und dem Code aus der ursprünglichen Bibliothek und die WinMD-Definitionen enthält, von JavaScript, C++ und die Verwendung der Windows-Runtime.|  
  
 Es sei denn, Sie geben `-target:module`, `-target` bewirkt, dass eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] -Assemblymanifest in eine Ausgabedatei hinzugefügt werden.  
  
 Jede Instanz des Vbc.exe erzeugt, die höchstens eine Ausgabedatei. Wenn Sie eine Compileroption, wie z. B. angeben `-out` oder `-target` mehrere Male, die letzte Lektion, die der Compiler verarbeitet in Kraft getreten ist. Informationen über alle Dateien in einer Kompilierung wird dem Manifest hinzugefügt. Alle Ausgabedateien außer erstellt mit `-target:module` Assemblymetadaten im Manifest enthalten. Verwendung [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1) zum Anzeigen der Metadaten in eine Ausgabedatei.  
  
 Die Kurzform von `-target` ist `-t`.  
  
### <a name="to-set--target-in-the-visual-studio-ide"></a>Um die set - Ziel, in der Visual Studio-IDE  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.   
  
2.  Klicken Sie auf die Registerkarte **Anwendung** .  
  
3.  Ändern Sie den Wert in der **Anwendungstyp** Feld.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `in.vb`, wodurch `in.dll`:  
  
```console
vbc -target:library in.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [-Referenz (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)  
 [Assemblys und der globale Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
