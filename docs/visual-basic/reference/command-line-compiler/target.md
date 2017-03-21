---
title: / target (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
caps.latest.revision: 29
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ccdb87188b924303057d5867dccece937defe74d
ms.lasthandoff: 03/13/2017

---
# <a name="target-visual-basic"></a>/target (Visual Basic)
Gibt das Format der Ausgabe des Compilers.  
  
## <a name="syntax"></a>Syntax  
  
```  
/target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die Auswirkung der `/target` Option.  
  
|**Option**|**Verhalten**|  
|----------------|------------------|  
|`/target:exe`|Der Compiler eine ausführbare Datei erstellen.<br /><br /> Dies ist die Standardoption, wenn keine `/target` angegeben wird. Die ausführbare Datei wird mit der Erweiterung .exe erstellt.<br /><br /> Sofern nicht anders angegeben mit der `/out` Option den Namen der Ausgabedatei erhält den Namen der Eingabedatei, die enthält die `Sub Main` Verfahren.<br /><br /> Nur ein `Sub Main` Verfahren ist erforderlich, in den Quellcodedateien, die in eine .exe-Datei kompiliert werden. Verwenden der `/main` -Compileroption angeben, welche Klasse enthält die `Sub Main` Verfahren.|  
|`/target:library`|Bewirkt, dass den Compiler eine Dynamic Link Library (DLL) zu erstellen.<br /><br /> Die Dynamic Link Library-Datei wird mit der Erweiterung ".dll" erstellt.<br /><br /> Sofern nicht anders angegeben mit der `/out` -Option den Namen der Ausgabedatei erhält den Namen der ersten Eingabedatei.<br /><br /> Beim Erstellen einer DLL eine `Sub Main` Verfahren ist nicht erforderlich.|  
|`/target:module`|Bewirkt, dass den Compiler ein Modul generiert, die eine Assembly hinzugefügt werden kann.<br /><br /> Die Ausgabedatei wird mit der Erweiterung .netmodule erstellt.<br /><br /> Die keine Assembly besitzt eine Datei kann von die .NET common Language Runtime kann nicht geladen werden. Sie können jedoch eine solche Datei in das Assemblymanifest einer Assembly integrieren, mithilfe von `/reference`.<br /><br /> Wenn Code in einem Modul auf interne Typen in einem anderen Modul verweist, müssen beide Module in ein Assemblymanifest aufgenommen werden, mithilfe von `/reference`.<br /><br /> Die [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) -Option importiert Metadaten aus einem Modul.|  
|`/target:winexe`|Bewirkt, dass den Compiler eine ausführbare Windows-basierte Anwendung erstellt.<br /><br /> Die ausführbare Datei wird mit der Erweiterung .exe erstellt. Eine Windows-basierte Anwendung ist eine, die eine Benutzeroberfläche entweder bietet die [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] -Klassenbibliothek oder mit den Win32-APIs.<br /><br /> Sofern nicht anders angegeben mit der `/out` Option den Namen der Ausgabedatei erhält den Namen der Eingabedatei, die enthält die `Sub Main` Verfahren.<br /><br /> Nur ein `Sub Main` Verfahren ist erforderlich, in den Quellcodedateien, die in eine .exe-Datei kompiliert werden. In Fällen, in denen der Code mehr als eine Klasse, die eine `Sub Main` Verfahren verwenden die `/main` -Compileroption angeben, welche Klasse enthält die `Sub Main` Verfahren|  
|`/target:appcontainerexe`|Bewirkt, dass den Compiler eine ausführbare Windows-basierte Anwendung erstellt, die in einem app-Container ausgeführt werden muss. Diese Einstellung dient für zu verwendende [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)] Applications.<br /><br /> Die **Appcontainerexe** Einstellung legt ein bit im Feld Merkmale der [übertragbare ausführbare Datei](http://go.microsoft.com/fwlink/p/?LinkId=236960) Datei. Dieses Bit gibt an, dass die app in einem app-Container ausgeführt werden muss. Wenn dieses Bit festgelegt ist, tritt ein Fehler auf, wenn die `CreateProcess` -Methode versucht, die Anwendung außerhalb von einem app-Container zu starten. Abgesehen von dieser bit festlegen **/target: appcontainerexe** entspricht **/target: winexe**.<br /><br /> Die ausführbare Datei wird mit der Erweiterung .exe erstellt.<br /><br /> Sofern Sie mithilfe der `/out` Option den Namen der Ausgabedatei erhält den Namen der Eingabedatei, die enthält die `Sub Main` Verfahren.<br /><br /> Nur ein `Sub Main` Verfahren ist erforderlich, in den Quellcodedateien, die in eine .exe-Datei kompiliert werden. Wenn der Code mehr als eine Klasse enthält, hat einen `Sub Main` Verfahren verwenden die `/main` -Compileroption angeben, welche Klasse enthält die `Sub Main` Verfahren|  
|`/target:winmdobj`|Bewirkt, dass den Compiler eine temporäre Datei erstellt, die Sie in einer Windows-Runtime-Binärdatei (.winmd) konvertieren können. Die winmd-Datei kann von JavaScript und C++-Programmen verwalteten Sprachprogrammen verwendet werden.<br /><br /> Die temporäre Datei wird mit der Erweiterung winmdobj erstellt.<br /><br /> Sofern Sie mithilfe der `/out` -Option den Namen der Ausgabedatei erhält den Namen der ersten Eingabedatei. Ein `Sub Main` Verfahren ist nicht erforderlich.<br /><br /> Die winmdobj-Datei als Eingabe für verwendet werden soll die <xref:Microsoft.Build.Tasks.WinMDExp>Tool zum Erstellen einer Windows-Metadaten (WinMD)-Datei exportieren.</xref:Microsoft.Build.Tasks.WinMDExp> Die WinMD-Datei hat die Erweiterung winmd und enthält sowohl dem Code aus der ursprünglichen Bibliothek und die WinMD-Definitionen, JavaScript, C++ und die Windows-Runtime-Verwendung.|  
  
 Es sei denn, Sie geben `/target:module`, `/target` bewirkt, dass eine [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] -Assemblymanifest in eine Ausgabedatei hinzugefügt werden.  
  
 Jede Instanz von Vbc.exe erzeugt, die höchstens eine Ausgabedatei. Wenn Sie eine Compileroption, wie z. B. angeben `/out` oder `/target` mehr als einmal, den letzten Datensatz der Compiler verarbeitet in Kraft getreten ist. Informationen über alle Dateien in einer Kompilierung wird das Manifest hinzugefügt. Alle Ausgabedateien mit Ausnahme derjenigen mit erstellten `/target:module` Assemblymetadaten im Manifest enthalten. Verwendung [Ildasm.exe (IL-Disassembler)](https://msdn.microsoft.com/library/f7dy01k1) um die Metadaten in einer Ausgabedatei anzuzeigen.  
  
 Die Kurzform der `/target` ist `/t`.  
  
### <a name="to-set-target-in-the-visual-studio-ide"></a>So legen Sie/Target in Visual Studio-IDE fest  
  
1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die Registerkarte **Anwendung** .  
  
3.  Ändern Sie den Wert in der **Anwendungstyp** Feld.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `in.vb`oder `in.dll`:  
  
```  
vbc /target:library in.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [/ out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)   
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [/ addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)   
 [/ moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)   
 [Assemblys und dem globalen Assemblycache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
