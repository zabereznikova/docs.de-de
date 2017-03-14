---
title: "/target:appcontainerexe (C#-Compileroptionen) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /target:appcontainerexe (C#-Compileroptionen)
Wenn Sie die **\/target:appcontainerexe**\-Compileroption verwenden, erstellt der Compiler eine ausführbare Windows\-Datei \(.exe\), die in einem App\-Container ausgeführt werden muss.  Diese Option entspricht [\/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), ist aber für [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)]\-Apps vorgesehen.  
  
## Syntax  
  
```  
/target:appcontainerexe  
```  
  
## Hinweise  
 Um festzulegen, dass die App in einem App\-Container ausgeführt werden muss, legt diese Option ein Bit in der [portierbaren ausführbaren](http://go.microsoft.com/fwlink/p/?LinkId=236960) Datei \(Portable Executable, PE\) fest.  Wenn dieses Bit festgelegt ist, tritt ein Fehler auf, wenn die CreateProcess\-Methode versucht, die ausführbare Datei außerhalb eines App\-Containers zu starten.  
  
 Sofern Sie nicht die Option [\/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) verwenden, erhält die Ausgabedatei den Namen der Eingabedatei, die die [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)\-Methode enthält.  
  
 Wenn Sie diese Option an einer Eingabeaufforderung festlegen, werden alle Dateien bis zur nächsten **\/out**\- oder **\/target**\-Option verwendet, um die ausführbare Datei zu erstellen.  
  
### So legen Sie diese Compileroption in der IDE fest  
  
1.  Öffnen Sie im **Projektmappen\-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.  
  
2.  Wählen Sie auf der Registerkarte **Anwendung** in der Liste **Ausgabetyp** die Option **Windows Store\-App** aus.  
  
     Diese Option ist nur für [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)]\-App\-Vorlagen verfügbar.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Beispiel  
 Der folgende Befehl kompiliert `filename.cs` in eine ausführbare Windows\-Datei, die nur in einem App\-Container ausgeführt werden kann.  
  
```  
csc /target:appcontainerexe filename.cs  
```  
  
## Siehe auch  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [\/target:winexe \(Create a Windows Program\)](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)