---
title: -Ziel (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acf47b24446656a539400c825f3332a70d211dad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="-target-visual-basic"></a>-Ziel (Visual Basic)
Gibt das Format der Compilerausgabe an.  
  
## <a name="syntax"></a>Syntax  
  
```  
-target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle werden die Auswirkungen der zusammengefasst die `-target` Option.  
  
|**Option**|**Verhalten**|  
|----------------|------------------|  
|`-target:exe`|Bewirkt, dass der Compiler eine ausführbare Konsolenanwendung zu erstellen.<br /><br /> Dies ist die Standardoption, wenn keine `-target` angegeben wird. Die ausführbare Datei wird mit der Erweiterung .exe erstellt.<br /><br /> Sofern nicht anders angegeben mit der `/out` Option den Namen der Ausgabedatei erhält den Namen der Eingabedatei, die enthält die `Sub Main` Prozedur.<br /><br /> Nur ein `Sub Main` Verfahren ist erforderlich, in den Quellcodedateien, die in eine .exe-Datei kompiliert werden. Verwenden der `-main` -Compileroption angeben, welche Klasse enthält die `Sub Main` Prozedur.|  
|`-target:library`|Bewirkt, dass der Compiler eine Dynamic Link Library (DLL) zu erstellen.<br /><br /> Die Dynamic Link Library-Datei wird mit der Erweiterung ".dll" erstellt.<br /><br /> Sofern nicht anders angegeben mit der `-out` Option den Namen der Ausgabedatei erhält den Namen der ersten Eingabedatei.<br /><br /> Beim Erstellen einer DLL eine `Sub Main` Verfahren ist nicht erforderlich.|  
|`-target:module`|Bewirkt, dass den Compiler ein Modul generiert, die auf eine Assembly hinzugefügt werden können.<br /><br /> Die Ausgabedatei wird mit der Erweiterung NETMODULE-Datei erstellt.<br /><br /> Die .NET common Language Runtime kann keine Datei, die eine Assembly nicht laden. Sie können jedoch eine solche Datei in das Manifest einer Assembly einbinden, mithilfe von `-reference`.<br /><br /> Wenn Code in einem Modul interne Typen in einem anderen Modul verwiesen wird, müssen beide Module in ein Assemblymanifest integriert werden, indem `-reference`.<br /><br /> Die [- Addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) Option importiert Metadaten aus einem Modul.|  
|`-target:winexe`|Bewirkt, dass der Compiler eine ausführbare Windows-basierten Anwendung zu erstellen.<br /><br /> Die ausführbare Datei wird mit der Erweiterung .exe erstellt. Eine Windows-basierte Anwendung ist eine, bietet eine Benutzeroberfläche entweder aus, der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] -Klassenbibliothek oder den Win32-APIs.<br /><br /> Sofern nicht anders angegeben mit der `-out` Option den Namen der Ausgabedatei erhält den Namen der Eingabedatei, die enthält die `Sub Main` Prozedur.<br /><br /> Nur ein `Sub Main` Verfahren ist erforderlich, in den Quellcodedateien, die in eine .exe-Datei kompiliert werden. In Fällen, in denen der Code mehr als eine Klasse hat, verfügt, ein `Sub Main` Verfahren verwenden die `-main` -Compileroption angeben, welche Klasse enthält die `Sub Main` Prozedur|  
|`-target:appcontainerexe`|Bewirkt, dass der Compiler eine ausführbare Windows-basierten Anwendung zu erstellen, die in einem app-Container ausgeführt werden muss. Diese Einstellung ist für entwickelt werden [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] Anwendungen.<br /><br /> Die **Appcontainerexe** Einstellung legt ein bit im Feld Merkmale der [übertragbare ausführbare Datei](http://go.microsoft.com/fwlink/p/?LinkId=236960) Datei. Dieses Bit gibt an, dass die app in einem app-Container ausgeführt werden muss. Wenn dieses Bit festgelegt ist, tritt ein Fehler auf, wenn die `CreateProcess` Methode versucht, die Anwendung außerhalb von einem app-Container zu starten. Abgesehen von dieser-bit-Einstellung **-Target: Appcontainerexe** entspricht **-Target: Winexe**.<br /><br /> Die ausführbare Datei wird mit der Erweiterung .exe erstellt.<br /><br /> Sofern Sie mithilfe der `-out` Option den Namen der Ausgabedatei erhält den Namen der Eingabedatei, die enthält die `Sub Main` Prozedur.<br /><br /> Nur ein `Sub Main` Verfahren ist erforderlich, in den Quellcodedateien, die in eine .exe-Datei kompiliert werden. Wenn der Code mehr als eine Klasse enthält, hat eine `Sub Main` Verfahren verwenden die `-main` -Compileroption angeben, welche Klasse enthält die `Sub Main` Prozedur|  
|`-target:winmdobj`|Bewirkt, dass der Compiler eine Zwischendatei zu erstellen, die Sie in einer Windows-Runtime-Binärdatei (.winmd) konvertieren können. Die winmd-Datei kann von JavaScript und C++-Programmen verwalteten Sprachprogrammen genutzt werden.<br /><br /> Die Zwischendatei wird mit einer winmdobj-Erweiterung erstellt.<br /><br /> Sofern Sie mithilfe der `-out` Option den Namen der Ausgabedatei erhält den Namen der ersten Eingabedatei. Ein `Sub Main` Prozedur ist nicht erforderlich.<br /><br /> Die winmdobj-Datei als Eingabe für verwendet werden soll die <xref:Microsoft.Build.Tasks.WinMDExp> Tool zum Erstellen einer Windows-Metadaten (WinMD)-Datei exportieren. Die WinMD-Datei hat eine winmd-Erweiterung und enthält sowohl dem Code von der ursprünglichen Bibliothek als auch die WinMD-Definitionen, JavaScript, C++ und die Verwendung der Windows-Runtime.|  
  
 Es sei denn, Sie geben `-target:module`, `-target` bewirkt, dass eine [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Assemblymanifest in eine Ausgabedatei hinzugefügt werden.  
  
 Jede Instanz von Vbc.exe erzeugt, darf höchstens eine Ausgabedatei. Wenn Sie eine Compileroption, wie z. B. angeben `-out` oder `-target` mehr als einmal, das letzte Lesezeichen, die der Compiler verarbeitet in Kraft getreten ist. Informationen über alle Dateien in einer Kompilierung wird dem Manifest hinzugefügt. Alle Ausgabedateien mit Ausnahme derjenigen mit erstellt `-target:module` Assemblymetadaten im Manifest enthalten. Verwendung [Ildasm.exe (IL-Disassembler)](https://msdn.microsoft.com/library/f7dy01k1) So zeigen Sie die Metadaten in eine Ausgabedatei an.  
  
 Die Kurzform von `-target` ist `-t`.  
  
### <a name="to-set--target-in-the-visual-studio-ide"></a>Zum Festlegen von - Ziel in der Visual Studio-IDE  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.   
  
2.  Klicken Sie auf die Registerkarte **Anwendung** .  
  
3.  Ändern Sie den Wert in der **Anwendungstyp** Feld.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `in.vb`, Erstellen von `in.dll`:  
  
```console
vbc -target:library in.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [-Verweis (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)  
 [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)  
 [-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)  
 [Assemblys und der globale Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
