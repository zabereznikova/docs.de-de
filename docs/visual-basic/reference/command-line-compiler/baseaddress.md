---
title: "/baseaddress | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/baseaddress"
  - "baseaddress"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-baseaddress compiler option [Visual Basic]"
  - "/baseaddress compiler option [Visual Basic]"
  - "baseaddress compiler option [Visual Basic]"
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /baseaddress
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt beim Erstellen einer DLL eine Standardbasisadresse an.  
  
## Syntax  
  
```  
/baseaddress:address  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`address`|Erforderlich.  Die Basisadresse für die DLL.  Diese Adresse muss als Hexadezimalwert angegeben werden.|  
  
## Hinweise  
 Die Standardbasisadresse für eine DLL wird durch [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] festgelegt.  
  
 Beachten Sie, dass das niederwertige Wort in dieser Adresse gerundet wird.  Wenn Sie beispielsweise 0x11110001 angeben, wird dies auf 0x11110000 gerundet.  
  
 Zur Durchführung des Signierungsvorgangs für eine DLL verwenden Sie die `–R`\-Option des Strong Name\-Tools \(Sn.exe\).  
  
 Diese Option wird ignoriert, wenn das Ziel keine DLL ist.  
  
||  
|-|  
|So legen Sie \/baseaddress in der Visual Studio\-IDE fest|  
|1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf **Erweitert**.<br />4.  Ändern Sie den Wert im Feld **DLL\-Basisadresse**. **Note:**      Das Feld **DLL\-Basisadresse** Feld ist schreibgeschützt, wenn das Ziel keine DLL ist.|  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)