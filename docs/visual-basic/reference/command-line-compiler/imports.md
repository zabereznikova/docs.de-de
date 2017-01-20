---
title: "/imports (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "/imports compiler option [Visual Basic]"
  - "imports compiler option [Visual Basic]"
  - "-imports compiler option [Visual Basic]"
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /imports (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Importiert Namespaces aus der angegebenen Assembly.  
  
## Syntax  
  
```  
/imports:namespaceList  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`namespaceList`|Erforderlich.  Durch Kommas getrennte Liste der Namespaces, die importiert werden sollen.|  
  
## Hinweise  
 Mit der `/imports`\-Option wird jeder Namespace importiert, der in den aktuellen Quelldateien oder einer Assembly, auf die verwiesen wird, definiert ist.  
  
 Die Member eines mit `/imports` angegebenen Namespaces stehen in allen Quellcodedateien der Kompilierung zur Verfügung.  Verwenden Sie die [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)\-Anweisung, um einen Namespace in einer einzigen Quellcodedatei zu verwenden.  
  
||  
|-|  
|So legen Sie \/imports in der integrierten Entwicklungsumgebung von Visual Studio fest|  
|1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Verweise**.<br />3.  Geben Sie den Namespacenamen in das Feld neben der Schaltfläche **Benutzerimport hinzufügen** ein.<br />4.  Klicken Sie auf die Schaltfläche **Benutzerimport hinzufügen**.|  
  
## Beispiel  
 Der folgende Code wird kompiliert, wenn `/imports:system` angegeben wird.  
  
 [!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)