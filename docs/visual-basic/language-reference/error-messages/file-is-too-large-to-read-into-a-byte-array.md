---
title: "File is too large to read into a byte array | Microsoft Docs"
ms.custom: ""
ms.date: "12/08/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# File is too large to read into a byte array
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die Datei, die Sie in ein Bytearray zu lesen versuchen, ist größer als 4 GB.  Die `My.Computer.FileSystem.ReadAllBytes`\-Methode kann keine Dateien lesen, die diese Größe übersteigen.  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie einen <xref:System.IO.StreamReader>, um die Datei zu lesen.  Weitere Informationen finden Sie unter [Grundlagen zu Datei\-E\/A\-Vorgängen und dem Dateisystem in .NET Framework \(Visual Basic\)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>   
 <xref:System.IO.StreamReader>   
 [File Access with Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)   
 [How to: Read Text from Files with a StreamReader](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)