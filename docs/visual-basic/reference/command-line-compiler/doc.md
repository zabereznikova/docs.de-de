---
title: "/doc | Microsoft Docs"
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
  - "doc compiler option [Visual Basic]"
  - "-doc compiler option [Visual Basic]"
  - "/doc compiler option [Visual Basic]"
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# /doc
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Verarbeitet Dokumentationskommentare zu einer XML\-Datei.  
  
## Syntax  
  
```  
/doc[+ | -]  
' -or-  
/doc:file  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`+`  &#124; `-`|Optional.  Wenn Sie \+ oder nur `/doc` angeben, generiert der Compiler Dokumentationsinformationen und platziert diese in einer XML\-Datei.  Die Angabe von `-`  ist gleichbedeutend mit dem Weglassen von `/doc` und bewirkt, dass keine Dokumentationsinformationen erstellt werden.|  
|`file`|Erforderlich, wenn `/doc:` angegeben wird.  Legt die XML\-Ausgabedatei fest, in die die Kommentare aus den kompilierten Quellcodedateien gefüllt werden.  Wenn der Dateiname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen \(""\) ein.|  
  
## Hinweise  
 Die `/doc` Option steuert, ob der Compiler eine XML\-Datei generiert, die die Dokumentationskommentare enthält.  Wenn Sie die Syntax `/doc:``file` verwenden, gibt der `file`\-Parameter den Namen der XML\-Datei an.  Wenn `/doc` oder `/doc+` verwendet wird, entnimmt der Compiler den Namen der XML\-Datei der ausführbaren Datei oder Bibliothek, die vom Compiler erstellt wird.  Wenn Sie `/doc-` verwenden oder die `/doc`\-Option nicht angeben, erstellt der Compiler keine XML\-Datei.  
  
 In Quellcodedateien können Dokumentationskommentare den folgenden Definitionen vorausgehen:  
  
-   Benutzerdefinierte Typen, z. B. eine [Klasse](../../../visual-basic/language-reference/statements/class-statement.md) oder [Schnittstelle](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Member, z. B. ein Feld, ein [Ereignis](../../../visual-basic/language-reference/statements/event-statement.md), oder eine [Eigenschaft](../../../visual-basic/language-reference/statements/property-statement.md), [Funktion](../../../visual-basic/language-reference/statements/function-statement.md) oder [Unterroutine](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Um die generierte XML\-Datei mit dem [IntelliSense](/visual-studio/ide/using-intellisense)\-Feature von [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] zu verwenden, benennen Sie die XML\-Datei nach der Assembly, die unterstützt werden soll.  Stellen Sie sicher, dass sich XML\-Datei und Assembly im selben Verzeichnis befinden, damit auch die XML\-Datei gefunden wird, wenn im [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)]\-Projekt auf die Assembly verwiesen wird.  Für den erfolgreichen Einsatz des IntelliSense\-Features in Code, der in einem Projekt oder in Projekten, auf die ein Projekt verweist, enthalten ist, sind XML\-Dokumentationsdateien nicht erforderlich.  
  
 Sofern nicht mit `/target:module` kompiliert wird, enthält die XML\-Datei die Tags `<assembly></assembly>`.  Diese Tags geben den Namen der Datei an, die das Assemblymanifest für die Ausgabedatei der Kompilierung enthält.  
  
 Möglichkeiten, eine Dokumentation aus Kommentaren im Code zu generieren, finden Sie unter [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md).  
  
||  
|-|  
|So legen Sie \/doc in der integrierten Entwicklungsumgebung von Visual Studio fest|  
|1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Legen Sie den Wert im Feld **XML\-Dokumentationsdatei generieren** fest.|  
  
## Beispiel  
 Ein Beispiel finden Sie unter [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md).  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)