---
title: "/rootnamespace | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/rootnamespace"
  - "rootnamespace"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/rootnamespace compiler option [Visual Basic]"
  - "-rootnamespace compiler option [Visual Basic]"
  - "rootnamespace compiler option [Visual Basic]"
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# /rootnamespace
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt einen Namespace für alle Typdeklarationen an.  
  
## Syntax  
  
```  
/rootnamespace:namespace  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`namespace`|Der Namespace, in den alle Typdeklarationen für das aktuelle Projekt aufgenommen werden sollen.|  
  
## Hinweise  
 Wenn Sie die ausführbare Datei \(Devenv.exe\) von Visual Studio zum Kompilieren eines in der integrierten Entwicklungsumgebung von Visual Studio erstellten Projekts verwenden, geben Sie mit `/rootnamespace` den Wert der <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>\-Eigenschaft an.  Weitere Informationen finden Sie unter [Devenv\-Befehlszeilenschalter](/visual-studio/ide/reference/devenv-command-line-switches).  
  
 Mit MSIL\-Disassembler \(`ldasm.exe`\) der Common Language Runtime können die Namespacenamen in der Ausgabedatei angezeigt werden.  
  
||  
|-|  
|So legen Sie \/rootnamespace in der integrierten Entwicklungsumgebung von Visual Studio fest|  
|1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Anwendung**.<br />3.  Ändern Sie den Wert im Feld **Stammnamespace**.|  
  
## Beispiel  
 Mit dem folgenden Code wird `In.vb` kompiliert, und alle Typdeklarationen werden in den `mynamespace`\-Namespace aufgenommen.  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Ildasm.exe \(IL Disassembler\)](../Topic/Ildasm.exe%20\(IL%20Disassembler\).md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)