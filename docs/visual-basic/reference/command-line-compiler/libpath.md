---
title: "/libpath | Microsoft Docs"
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
  - "libpath compiler option [Visual Basic]"
  - "/libpath compiler option [Visual Basic]"
  - "-libpath compiler option [Visual Basic]"
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /libpath
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt den Speicherort von Assemblys an, auf die verwiesen wird.  
  
## Syntax  
  
```  
/libpath:dirList  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`dirList`|Erforderlich.  Eine durch Semikolons getrennte Liste von Verzeichnissen, die der Compiler durchsucht, wenn eine Assembly, auf die verwiesen wird, nicht im aktuellen Arbeitsverzeichnis \(dem Verzeichnis, von dem aus Sie den Compiler starten\) oder im Systemverzeichnis der Common Language Runtime gefunden wird.  Wenn der Verzeichnisname ein Leerzeichen enthält, schließen Sie den Namen in Anführungszeichen \(""\) ein.|  
  
## Hinweise  
 Die `/libpath`\-Option gibt den Speicherort von Assemblys an, auf die mit der [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)\-Option verwiesen wird.  
  
 Der Compiler sucht in der folgenden Reihenfolge nach Assemblyverweisen, die nicht voll qualifiziert sind:  
  
1.  Aktuelles Arbeitsverzeichnis.  Dies ist das Verzeichnis, von dem aus der Compiler aufgerufen wurde.  
  
2.  Systemverzeichnis der Common Language Runtime.  
  
3.  Durch `/libpath` angegebene Verzeichnisse.  
  
4.  Verzeichnisse, die durch die **LIB**\-Umgebungsvariable angegeben werden.  
  
 Die  `/libpath`\-Option ist additiv. Wenn Sie sie mehrmals angeben, werden die entsprechenden Werte an die vorherigen Werte angehängt.  
  
 Verwenden Sie `/reference`, um einen Assemblyverweis anzugeben.  
  
||  
|-|  
|So legen Sie \/libpath in der integrierten Entwicklungsumgebung von Visual Studio fest|  
|1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Verweise**.<br />3.  Klicken Sie auf die Schaltfläche **Verweispfade**.<br />4.  Geben Sie im Dialogfeld **Verweispfade** den Verzeichnisnamen im Feld **Ordner** ein.<br />5.  Klicken Sie auf **Ordner hinzufügen**.|  
  
## Beispiel  
 Mit dem folgenden Code wird `T2.vb` kompiliert und eine EXE\-Datei erstellt.  Der Compiler sucht im Arbeitsverzeichnis, im Stammverzeichnis von Laufwerk C: und im Verzeichnis New Assemblies von Laufwerk C: nach Assemblyverweisen.  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## Siehe auch  
 [Assemblys und der globale Assemblycache](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)