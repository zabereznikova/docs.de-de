---
title: "How to: Validate File Names and Paths in Visual Basic | Microsoft Docs"
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
  - "file names, validating"
  - "strings [Visual Basic], validating"
  - "Boolean values"
  - "paths, validating"
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# How to: Validate File Names and Paths in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

In diesem Beispiel wird ein `Boolean`\-Wert zurückgegeben, der angibt, ob eine Zeichenfolge einen Dateinamen oder einen Pfad darstellt.  Bei der Validierung wird überprüft, ob der Name Zeichen enthält, die im Dateisystem nicht zulässig sind.  
  
## Beispiel  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/visualbasic/how-to-validate-file-nam_1.vb)]  
  
 In diesem Beispiel wird nicht überprüft, ob der Name Doppelpunkte an der falschen Position oder Verzeichnisse ohne einen Namen enthält oder ob die Länge des Namens die vom System definierte maximale Länge überschreitet.  Es wird auch nicht überprüft, ob die Anwendung über die Berechtigung für den Zugriff auf die Dateisystemressource mit dem angegebenen Namen verfügt.  
  
## Siehe auch  
 <xref:System.IO.Path.GetInvalidPathChars%2A>   
 [Validating Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)