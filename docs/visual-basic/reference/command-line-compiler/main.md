---
title: "/main | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "main compiler option [Visual Basic]"
  - "/main compiler option [Visual Basic]"
  - "-main compiler option [Visual Basic]"
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /main
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt die Klasse oder das Modul an, die bzw. das die `Sub Main`\-Prozedur enthält.  
  
## Syntax  
  
```  
/main:location  
```  
  
## Argumente  
 `location`  
 Erforderlich.  Eine vollständige Qualifizierung der Klasse oder des Moduls mit der `Sub Main`\-Prozedur, die beim Programmstart aufgerufen werden soll.  Diese kann das Format **\/main:module** oder **\/main:namespace.module** aufweisen.  
  
## Hinweise  
 Verwenden Sie diese Option beim Erstellen einer ausführbaren Datei oder eines ausführbaren Windows\-Programms.  Wenn Sie die **\/main**\-Option weglassen, sucht der Compiler in allen öffentlichen Klassen und Modulen nach einer gültigen gemeinsam genutzten `Sub Main`.  
  
 Die verschiedenen Formen der `Main`\-Prozedur werden unter [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) erläutert.  
  
 Wenn `location` eine Klasse ist, die von <xref:System.Windows.Forms.Form> erbt, stellt der Compiler eine `Main`\-Standardprozedur bereit, die die Anwendung startet, wenn die Klasse über keine `Main`\-Prozedur verfügt.  Dadurch können Sie Code in der Befehlszeile kompilieren, der in der Entwicklungsumgebung erstellt wurde.  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/visualbasic/main_1.vb)]  
  
### So legen Sie \/main in der integrierten Entwicklungsumgebung von Visual Studio fest  
  
1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
     Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Klicken Sie auf die Registerkarte **Anwendung**.  
  
3.  Stellen Sie sicher, dass das Kontrollkästchen **Anwendungsframework aktivieren** nicht aktiviert ist.  
  
4.  Ändern Sie den Wert im Feld **Startobjekt**.  
  
## Beispiel  
 Mit dem folgenden Code werden `T2.vb` und `T3.vb` kompiliert. Dabei wird angegeben, dass sich die `Sub Main`\-Prozedur in der `Test2`\-Klasse befindet.  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/de-de/9d030b60-e148-4366-a462-69532f02294c)   
 [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)