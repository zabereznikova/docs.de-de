---
title: "How to: Refer to an Enumeration Member (Visual Basic) | Microsoft Docs"
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
  - "enumerations [Visual Basic], referring to"
  - "values, associating constant values with names"
  - "enumeration members"
  - "constants, enumerated"
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Refer to an Enumeration Member (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Enumerationen sind eine praktische Möglichkeit, mit Gruppen von verwandten Konstanten zu arbeiten und Konstantenwerte mit Namen zu verbinden.  Sie können beispielsweise eine Enumeration für eine Reihe von Ganzzahlkonstanten deklarieren, die mit den Wochentagen verknüpft sind. Anschließend können Sie anstelle der Ganzzahlwerte im Code die Namen der einzelnen Tage verwenden.  
  
 Mit der `Imports`\-Anweisung können Sie die Verwendung voll qualifizierter Namen vermeiden.  Weitere Informationen hierzu finden Sie unter [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
### So verweisen Sie auf einen Enumerationsmember  
  
-   Qualifizieren Sie den Membernamen mit der Enumeration.  Im folgenden Beispiel wird der `Saturday`\-Member der `FirstDayOfWeek`\-Enumeration der Variablen `DayValue` zugewiesen.  
  
     [!code-vb[VbEnumsTask#19](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/WindowsApplication1/Class2.vb#19)]  
  
## Siehe auch  
 [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)