---
title: "/target:winmdobj (C#-Compileroptionen) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /target:winmdobj (C#-Compileroptionen)
Wenn Sie die **\/target:winmdobj**\-Compileroption verwenden, erstellt der Compiler eine WINMDOBJ\-Zwischendatei, die Sie in eine binäre Windows\-Runtime\-Datei \(.winmd\) konvertieren können.  Die WINMD\-Datei kann dann von verwalteten Sprachprogrammen und auch von JavaScript\- und C\+\+\-Programmen verwendet werden.  
  
## Syntax  
  
```  
/target:winmdobj  
```  
  
## Hinweise  
 Die **winmdobj**\-Einstellung signalisiert dem Compiler, dass ein Zwischenmodul erforderlich ist.  Als Antwort darauf kompiliert Visual Studio die C\#\-Klassenbibliothek als WINMDOBJ\-Datei.  Die WINMDOBJ\-Datei kann dann durch das <xref:Microsoft.Build.Tasks.WinMDExp>\-Exporttool eingegeben werden, um eine Windows\-Metadatendatei \(.winmd\) zu erzeugen.  Die WINMD\-Datei enthält sowohl den Code von der ursprünglichen Bibliothek als auch die WinMD\-Metadaten, die von JavaScript oder C\+\+ und von der Windows\-Runtime verwendet werden.  
  
 Die Ausgabe einer Datei, die mithilfe der **\/target:winmdobj**\-Compileroption kompiliert wird, ist für die reine Verwendung als Eingabe für das WimMDExp\-Exporttool vorgesehen. Auf die WINMDOBJ\-Datei selbst wird nicht direkt verwiesen.  
  
 Sofern Sie nicht die Option [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) verwenden, erhält die Ausgabedatei den Namen der ersten Eingabedatei.  Eine [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)\-Methode ist nicht erforderlich.  
  
 Wenn Sie die \/target:winmdobj\-Option an einer Eingabeaufforderung festlegen, werden alle Dateien bis zur nächsten **\/out**\- oder [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md)\-Option verwendet, um das Windows\-Programm zu erstellen.  
  
### So legen Sie diese Compileroption in der Visual Studio\-IDE für eine Windows Store\-App fest  
  
1.  Öffnen Sie im **Projektmappen\-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.  
  
2.  Wählen Sie die Registerkarte **Anwendung** aus.  
  
3.  Wählen Sie in der Liste **Ausgabetyp** die Option **WinMD\-Datei** aus.  
  
     Die Option **WinMD\-Datei** ist nur für [!INCLUDE[win8_appname_long](../../../csharp/includes/win8-appname-long-md.md)]\-App\-Vorlagen verfügbar.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Beispiel  
 Der folgende Befehl kompiliert `filename.cs` in eine WINMDOBJ\-Zwischendatei.  
  
```  
csc /target:winmdobj filename.cs  
```  
  
## Siehe auch  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)