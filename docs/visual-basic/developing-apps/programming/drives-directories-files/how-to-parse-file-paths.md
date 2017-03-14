---
title: "Gewusst wie: Analysieren von Dateipfaden in Visual Basic | Microsoft Docs"
ms.custom: ""
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
  - "Dateinamen, Analysieren [Visual Basic]"
  - "Analysieren, Dateipfade [Visual Basic]"
ms.assetid: c1bd99c9-8160-456a-b5ab-60a49139b923
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Gewusst wie: Analysieren von Dateipfaden in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Das <xref:Microsoft.VisualBasic.FileIO.FileSystem>\-Objekt bietet eine Reihe nützlicher Methoden für die Analyse von Dateipfaden.  
  
-   Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>\-Methode übernimmt zwei Pfade und gibt einen korrekt formatierten kombinierten Pfad zurück.  
  
-   Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetParentPath%2A>\-Methode gibt den absoluten übergeordneten Pfad des bereitgestellten Pfads zurück.  
  
-   Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>\-Methode gibt ein <xref:System.IO.FileInfo>\-Objekt zurück, das abgefragt werden kann, um die Eigenschaften der Datei zu ermitteln, beispielsweise deren Name und Pfad.  
  
 Beurteilen Sie den Inhalt der Datei nicht anhand der Dateinamenerweiterung. Bei der Datei "Form1.vb" handelt es sich zum Beispiel nicht unbedingt um eine Visual Basic\-Quelldatei.  
  
### So ermitteln Sie den Namen und den Pfad einer Datei  
  
-   Verwenden Sie die <xref:System.IO.FileInfo.DirectoryName%2A>\- und die <xref:System.IO.FileInfo.Name%2A>\-Eigenschaft des <xref:System.IO.FileInfo>\-Objekts, um den Namen und den Pfad einer Datei zu ermitteln. In diesem Beispiel werden der Name und der Pfad ermittelt und angezeigt.  
  
     [!code-vb[VbVbcnMyFileSystem#54](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_1.vb)]  
  
### So kombinieren Sie den Namen und das Verzeichnis einer Datei, um den vollständigen Pfad zu erstellen  
  
-   Verwenden Sie die `CombinePath`\-Methode, und geben Sie das Verzeichnis und den Namen an. In diesem Beispiel werden die im vorherigen Beispiel erstellten Zeichenfolgen `folderPath` und `fileName` kombiniert, und das Ergebnis wird angezeigt.  
  
     [!code-vb[VbVbcnMyFileSystem#55](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-parse-file-paths_2.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CombinePath%2A>   
 <xref:System.IO.FileInfo>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>   
 [How to: Get the Collection of Files in a Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)