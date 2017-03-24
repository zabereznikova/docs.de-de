---
title: "/main (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/main"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-main compiler option [C#]"
  - "main compiler option [C#]"
  - "/main compiler option [C#]"
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# /main (C# Compiler Options)
Diese Option gibt die Klasse an, die den Einstiegspunkt des Programms enthält, wenn mehrere Klassen eine **Main**\-Methode enthalten.  
  
## Syntax  
  
```  
/main:class  
```  
  
## Argumente  
 `class`  
 der Typ, der die **Main**\-Methode enthält.  
  
## Hinweise  
 Wenn in der Kompilierung mehrere Typen mit einer [Main](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)\-Methode enthalten sind, können Sie festlegen, in welchem Typ die **Main**\-Methode enthalten ist, die Sie als Einstiegspunkt in das Programm verwenden möchten.  
  
 Diese Option ist für die Kompilierung von EXE\-Dateien vorgesehen.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite von **Anwendung**.  
  
3.  Ändern Sie die **Startobjekt**\-Eigenschaft.  
  
     Weitere Informationen zur programmgesteuerten Festlegung dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.  
  
## Beispiel  
 In diesem Beispiel werden `t2.cs` und `t3.cs` kompiliert, wobei angegeben wird, dass sich die relevante **Main**\-Methode in `Test2` befindet:  
  
```  
csc t2.cs t3.cs /main:Test2  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)