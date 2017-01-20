---
title: "Differences Between Properties and Variables in Visual Basic | Microsoft Docs"
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
  - "property values"
  - "variables [Visual Basic]"
  - "Visual Basic code, procedures"
  - "values, properties"
  - "variables [Visual Basic], definition"
  - "Visual Basic code, variables"
  - "Visual Basic code, properties"
  - "properties [Visual Basic], values"
  - "properties [Visual Basic], defined"
  - "variables [Visual Basic], and properties"
  - "properties [Visual Basic], and variables"
ms.assetid: 7a03a8be-5381-431f-bd7c-16e887e4e07b
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Differences Between Properties and Variables in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Variablen und Eigenschaften stellen jeweils Werte dar, auf die Sie zugreifen können.  Es gibt jedoch Unterschiede in Bezug auf Speicherung und Implementierung.  
  
## Variablen  
 Eine *Variable* entspricht direkt einer Speicheradresse.  Für die Definition einer Variablen reicht eine Deklarationsanweisung.  Eine Variable kann eine *lokale Variable* sein, die innerhalb einer Prozedur definiert ist und nur in dieser Prozedur verfügbar ist. Es kann sich aber auch um eine *Membervariable* handeln, die in einem Modul, einer Klasse oder einer Struktur definiert ist, jedoch nicht innerhalb einer Prozedur.  Eine Membervariable wird auch als *Feld* bezeichnet.  
  
## Eigenschaften  
 Eine *Eigenschaft* ist ein Datenelement, das in einem Modul, einer Klasse oder einer Struktur definiert ist.  Sie definieren eine Eigenschaft mit einem Codeblock, der zwischen den Anweisungen `Property` und `End Property` steht.  Der Codeblock enthält eine `Get`\-Prozedur, eine `Set`\-Prozedur oder beides.  Diese Prozeduren werden als *Eigenschaftenprozeduren* oder *Eigenschaftenaccessoren* bezeichnet.  Prozeduren können nicht nur den Wert der Eigenschaft abrufen oder speichern, sondern auch benutzerdefinierte Aktionen ausführen, etwa einen Zugriffszähler aktualisieren.  
  
## Unterschiede  
 In der folgenden Tabelle werden einige wichtige Unterschiede zwischen Variablen und Eigenschaften dargestellt.  
  
|Unterscheidungsmerkmal|Variable|Property|  
|----------------------------|--------------|--------------|  
|Deklaration|Einzelne Deklarationsanweisung|Reihe von Anweisungen in einem Codeblock|  
|Implementierung|Einzelner Speicherort|Ausführbarer Code \(Eigenschaftenprozeduren\)|  
|Speicherung|Direkt dem Wert der Variablen zugeordnet|I. d. R. interne Speicherung, nicht verfügbar außerhalb der enthaltenden Klasse oder des Moduls der Eigenschaft<br /><br /> Der Wert der Eigenschaft muss nicht unbedingt als gespeichertes Element<sup>1</sup> existieren.|  
|Ausführbarer Code|None|Muss wenigstens eine Prozedur enthalten|  
|Lese\- und Schreibzugriff|Lese\-\/Schreibzugriff oder schreibgeschützt|Lese\-\/Schreibzugriff, schreibgeschützt oder lesegeschützt|  
|Benutzerdefinierte Aktionen \(neben Akzeptieren oder Zurückgeben eines Werts\)|Nicht möglich|Können beim Festlegen oder Abrufen des Eigenschaftswerts ausgeführt werden.|  
  
 <sup>1</sup> Im Unterschied zu einer Variablen entspricht der Wert einer Eigenschaft eventuell nicht direkt einem bestimmten Speicherelement.  Das Speicherelement ist aus praktischen oder sicherheitstechnischen Gründen unter Umständen in mehrere Abschnitte aufgeteilt, oder der Wert wird möglicherweise verschlüsselt gespeichert.  In diesen Fällen setzt die `Get`\-Prozedur die Abschnitte zusammen oder entschlüsselt den gespeicherten Wert, während die `Set`\-Prozedur den neuen Wert verschlüsselt oder das Speicherelement in mehrere Abschnitte aufteilt.  Ein Eigenschaftswert, wie beispielsweise die Tageszeit, kann begrenzte Lebensdauer haben. In diesem Fall würde er von der `Get`\-Prozedur spontan berechnet, sobald Sie auf die Eigenschaft zugreifen.  
  
## Siehe auch  
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)