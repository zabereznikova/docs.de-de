---
title: "/target (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "target compiler options [Visual Basic]"
  - "-target compiler options [Visual Basic]"
  - "/target compiler options [Visual Basic]"
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
caps.latest.revision: 29
caps.handback.revision: 29
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /target (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt das Format der Compilerausgabe an.  
  
## Syntax  
  
```  
/target:{exe | library | module | winexe | appcontainerexe | winmdobj}  
```  
  
## Hinweise  
 In der folgenden Tabelle wird die Wirkung der `/target`\-Option zusammengefasst.  
  
|**Option**|**Verhalten**|  
|----------------|-------------------|  
|`/target:exe`|Bewirkt, dass der Compiler eine ausführbare Konsolenanwendung erstellt.<br /><br /> Dies ist die Standardoption, wenn keine `/target`\-Option angegeben wurde.  Die ausführbare Datei wird mit der Erweiterung EXE erstellt.<br /><br /> Sofern nicht durch die `/out`\-Option anders angegeben, erhält die Ausgabedatei den Namen derjenigen Eingabedatei, welche die `Sub Main`\-Prozedur enthält.<br /><br /> In den Quellcodedateien, die zu einer EXE\-Datei kompiliert werden, wird nur eine `Sub Main`\-Prozedur benötigt.  Verwenden Sie die `/main`\-Compileroption, um anzugeben, welche Klasse die `Sub Main`\-Prozedur enthält.|  
|`/target:library`|Bewirkt, dass der Compiler eine Dynamic Link Library \(DLL\) erstellt.<br /><br /> Die Dynamic\-Link\-Library\-Datei wird mit der Erweiterung **.dll** erstellt.<br /><br /> Sofern nicht durch die `/out`\-Option anders angegeben, erhält die Ausgabedatei den Namen der ersten Eingabedatei.<br /><br /> Beim Erstellen einer DLL wird keine `Sub Main`\-Prozedur benötigt.|  
|`/target:module`|Bewirkt, dass der Compiler ein Modul generiert, das einer Assembly hinzugefügt werden kann.<br /><br /> Die Ausgabedatei erhält die Dateinamenerweiterung .  netmodule.<br /><br /> Die .NET\-Common Language Runtime kann eine Datei ohne Assembly nicht laden.  Allerdings können Sie eine solche Datei mithilfe von `/reference` in das Assemblymanifest einer Assembly aufnehmen.<br /><br /> Wenn Code in einem Modul auf interne Typen in einem anderen Modul verweist, müssen beide Module mithilfe von `/reference` in ein Assemblymanifest aufgenommen werden.<br /><br /> Die [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)\-Option importiert Metadaten aus einem Modul.|  
|`/target:winexe`|Bewirkt, dass der Compiler eine ausführbare Windows\-basierte Anwendung erstellt.<br /><br /> Die ausführbare Datei wird mit der Erweiterung EXE erstellt.  Eine Windows\-basierte Anwendung ist eine Anwendung, die eine Benutzeroberfläche entweder aus der [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Klassenbibliothek oder aus den Win32\-APIs bereitstellt.<br /><br /> Sofern nicht durch die `/out`\-Option anders angegeben, erhält die Ausgabedatei den Namen derjenigen Eingabedatei, welche die `Sub Main`\-Prozedur enthält.<br /><br /> In den Quellcodedateien, die zu einer EXE\-Datei kompiliert werden, wird nur eine `Sub Main`\-Prozedur benötigt.  Falls im Code mehr als eine Klasse mit einer `Sub Main`\-Prozedur vorhanden ist, geben Sie mithilfe der `/main`\-Compileroption an, welche Klasse die `Sub Main`\-Prozedur enthält.|  
|`/target:appcontainerexe`|Bewirkt, dass der Compiler eine ausführbare Windows\-basierte Anwendung zu erstellen, die in einem App\-Container ausgeführt werden muss.  Diese Einstellung ist so konzipiert, [!INCLUDE[win8_appname_long](../../../csharp/includes/win8-appname-long-md.md)] für Anwendungen verwendet werden.<br /><br /> **appcontainerexe**, das Sätze ein Bit auf dem Eigenschaftengebiet der [PE\-Datei](http://go.microsoft.com/fwlink/p/?LinkId=236960) Datei festgelegt wird.  Dieses Bit gibt an, dass die Anwendung in einen App\-Container ausgeführt werden muss.  Wenn dieses Bit festgelegt ist, tritt ein Fehler auf, wenn die `CreateProcess`\-Methode versucht, zum Starten der Anwendung außerhalb eines App\-Containers.  Neben dieser Biteinstellung ist **\/target:appcontainerexe** zu **\/target:winexe** entsprechend.<br /><br /> Die ausführbare Datei wird mit der Erweiterung EXE erstellt.<br /><br /> Es sei denn, Sie anders festlegen, indem Sie die Option `/out` verwenden, übernimmt der Ausgabedatei den Namen der Eingabedatei, die die `Sub Main` Prozedur enthält.<br /><br /> In den Quellcodedateien, die zu einer EXE\-Datei kompiliert werden, wird nur eine `Sub Main`\-Prozedur benötigt.  Wenn der Code mehr als eine Klasse enthält, die eine `Sub Main` Prozedur verfügt, verwenden Sie die \- Compileroption `/main` anzugeben, der \- Klasse, die `Sub Main` Prozedur enthält|  
|`/target:winmdobj`|Bewirkt, dass der Compiler eine Zwischendatei zu erstellen, die Sie einer binären \(.winmd\) Datei der Windows Runtime konvertieren können.  Die WINMD\-Datei kann durch JavaScript\- und C\+\+\-Programmen, neben den verwalteten Sprachenprogrammen genutzt werden.<br /><br /> Die Zwischendatei wird mit einer .winmdobj\-Erweiterung erstellt.<br /><br /> Es sei denn, Sie anders festlegen, indem Sie die Option `/out` verwenden, übernimmt die Ausgabedatei den Namen der ersten Eingabedatei.  Eine `Sub Main` Prozedur ist nicht erforderlich.<br /><br /> Die WINMDOBJ\-Datei wurde entworfen, als Eingabe verwendet werden, sodass das <xref:Microsoft.Build.Tasks.WinMDExp> Exporttool eine Datei Windows\-Metadaten \(WinMD\) erzeugt.  Die WinMD\-Datei verfügt über eine .winmd\-Erweiterung und enthält den Code aus der ursprünglichen Bibliothek und die WinMD\-Definitionen, die JavaScript, C\+\+ und die Windows Runtime verwendet.|  
  
 Wenn Sie kein `/target:module` festlegen, wird von `/target` einer Ausgabedatei ein [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Assemblymanifest hinzugefügt.  
  
 Jede Instanz von Vbc.exe erzeugt höchstens eine Ausgabedatei.  Wird eine Compileroption wie `/out` oder `/target` mehrfach angegeben, ist die vom Compiler zuletzt erkannte wirksam.  Informationen über alle Dateien in einer Kompilierung werden in das Assemblymanifest geschrieben.  Alle Ausgabedateien mit Ausnahme der mit `/target:module` erstellten Dateien können Assemblymetadaten im Manifest enthalten.  Verwenden Sie den [Ildasm.exe \(IL Disassembler\)](../Topic/Ildasm.exe%20\(IL%20Disassembler\).md), um die Metadaten in einer Ausgabedatei anzuzeigen.  
  
 Die Kurzform von `/target` ist `/t`.  
  
### So legen Sie \/target in der Visual Studio\-IDE fest  
  
1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die Registerkarte **Anwendung**.  
  
3.  Ändern Sie den Wert im Feld **Anwendungstyp**.  
  
## Beispiel  
 Im folgenden Code wird `in.vb` kompiliert und `in.dll` erstellt:  
  
```  
vbc /target:library in.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [\/out](../../../visual-basic/reference/command-line-compiler/out.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)   
 [\/moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)   
 [Assemblys und der globale Assemblycache](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)