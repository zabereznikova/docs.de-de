---
title: "How to: Iterate Through An Enumeration in Visual Basic | Microsoft Docs"
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
  - "arrays [Visual Basic], iterating"
  - "enumerations [Visual Basic], iterating"
  - "ListBox control [Windows Forms], populating from an enumeration"
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# How to: Iterate Through An Enumeration in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Enumerationen bieten eine bequeme Möglichkeit, mit Gruppen verwandter Konstanten zu arbeiten und Konstantenwerte mit Namen zu verknüpfen.  Um eine Enumeration zu durchlaufen, können Sie sie mit der <xref:System.Enum.GetValues%2A>\-Methode in ein Array verschieben.  Sie können dazu aber auch eine `For...Each`\-Anweisung verwenden. Extrahieren Sie dazu die Zeichenfolge oder den numerischen Wert mit der <xref:System.Enum.GetNames%2A>\-Methode bzw. der <xref:System.Enum.GetValues%2A>\-Methode.  
  
### So durchlaufen Sie eine Enumeration  
  
-   Deklarieren Sie ein Array, und konvertieren Sie die Enumeration mit der <xref:System.Enum.GetValues%2A>\-Methode in das Array, bevor Sie das Array wie eine Variable übergeben.  Im folgenden Beispiel werden die einzelnen Member der Enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> beim Durchlaufen der Enumeration gezeigt.  
  
     [!code-vb[VbEnumsTask#7](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/WindowsApplication1/Class2.vb#7)]  
  
## Siehe auch  
 [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)   
 [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)