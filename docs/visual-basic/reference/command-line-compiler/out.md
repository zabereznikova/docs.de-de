---
title: "/out (Visual Basic) | Microsoft Docs"
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
  - "/out compiler option [Visual Basic]"
  - "-out compiler option [Visual Basic]"
  - "out compiler option [Visual Basic]"
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /out (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt den Namen der Ausgabedatei an.  
  
## Syntax  
  
```  
/out:filename  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`filename`|Erforderlich.  Der Name der vom Compiler erstellten Ausgabedatei.  Wenn der Dateiname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen \(" "\) ein.|  
  
## Hinweise  
 Geben Sie den vollständigen Namen und die Dateinamenerweiterung der zu erstellenden Datei an.  Andernfalls bezieht die EXE\-Datei ihren Namen von der Quellcodedatei, in der die `Sub Main`\-Prozedur gespeichert ist. Die DLL\-Datei erhält ihren Namen von der ersten Quellcodedatei.  
  
 Wenn Sie einen Dateinamen ohne die Erweiterung ".exe" oder ".dll" angeben, wird die Erweiterung entsprechend dem für die `/target`\-Compileroption angegebenen Wert vom Compiler automatisch hinzugefügt.  
  
||  
|-|  
|So legen Sie \/out in der integrierten Entwicklungsumgebung von Visual Studio fest|  
|1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Anwendung**.<br />3.  Ändern Sie den Wert im Feld **Assemblyname**.|  
  
## Beispiel  
 Im folgenden Code wird `T2.vb` kompiliert und die Ausgabedatei `T2.exe` erstellt:  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)