---
title: "Zero-based vs. One-based String Access in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
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
  - "strings [Visual Basic], indexing"
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Zero-based vs. One-based String Access in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In diesem Thema wird verglichen, wie [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] und [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] den Zugriff auf die Zeichen in einer Zeichenfolge ermöglichen.  [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] ermöglicht immer den nullbasierten Zugriff auf die Zeichen in einer Zeichenfolge, während [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] je nach Funktion nullbasierten oder 1\-basierten Zugriff ermöglicht.  
  
## 1\-basiert  
 Ein Beispiel für eine 1\-basierte [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Funktion ist die `Mid`\-Funktion.  Die Funktion erhält ein Argument, das die Zeichenposition angibt, an der die Teilzeichenfolge beginnt \(Beginn an Position 1\).  Die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=fullName>\-Methode erhält einen Index des Zeichens in die Zeichenfolge, an der die Teilzeichenfolge beginnen soll \(Beginn an Position 0\).  Wenn daher die Zeichenfolge "ABCDE" lautet, werden die einzelnen Zeichen für die Verwendung mit der `Mid`\-Funktion mit 1,2,3,4,5, für die Verwendung mit der <xref:System.String.Substring%2A?displayProperty=fullName>\-Methode jedoch mit 0,1,2,3,4 nummeriert.  
  
## Nullbasiert  
 Betrachten Sie als Beispiel einer auf null basierenden [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Funktion die `Split`\-Funktion.  Sie teilt eine Zeichenfolge und gibt ein Array zurück, das die Teilzeichenfolgen enthält.  Auch die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=fullName>\-Methode teilt eine Zeichenfolge und gibt ein Array zurück, das die Teilzeichenfolgen enthält.  Da die `Split`\-Funktion und die <xref:System.String.Split%2A>\-Methode [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Arrays zurückgeben, müssen sie nullbasiert sein.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>   
 <xref:Microsoft.VisualBasic.Strings.Split%2A>   
 <xref:System.String.Substring%2A>   
 <xref:System.String.Split%2A>   
 [Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)