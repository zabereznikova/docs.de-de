---
title: "Doppelte Anf&#252;hrungszeichen sind kein g&#252;ltiges Kommentartoken f&#252;r Felder mit Trennzeichen, bei denen HasFieldsEnclosedInQuotes auf &quot;True&quot; festgelegt ist. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrTextFieldParser_InvalidComment"
dev_langs: 
  - "VB"
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Doppelte Anf&#252;hrungszeichen sind kein g&#252;ltiges Kommentartoken f&#252;r Felder mit Trennzeichen, bei denen HasFieldsEnclosedInQuotes auf &quot;True&quot; festgelegt ist.
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Als Trennzeichen für den `TextFieldParser` wurde ein Anführungszeichen angegeben, aber `EscapeQuotes` ist auf `True` festgelegt.  
  
### So beheben Sie diesen Fehler  
  
-   Legen Sie `EscapeQuotes` auf `False` fest.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>   
 [How to: Read From Comma\-Delimited Text Files](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)