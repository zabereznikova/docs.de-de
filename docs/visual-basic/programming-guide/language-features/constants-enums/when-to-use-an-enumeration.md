---
title: "When to Use an Enumeration (Visual Basic) | Microsoft Docs"
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
  - "enumerations [Visual Basic]"
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# When to Use an Enumeration (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Enumerationen vereinfachen die Arbeit mit einem Satz verwandter Konstanten.  Eine Enumeration \(`Enum`\) ist ein symbolischer Name für eine Gruppe von Werten.  Enumerationen werden als Datentypen behandelt. Mit ihrer Hilfe können Sie Konstanten erstellen, die für Variablen und Eigenschaften verwendet werden.  
  
## Situationen für die Verwendung von Enumerationen  
 Sobald eine Prozedur eine begrenzte Menge von Variablen annimmt, können Sie die Verwendung einer Enumeration in Betracht ziehen.  Durch Enumerationen wird Code besser lesbar, insbesondere wenn aussagekräftige Namen verwendet werden.  
  
 Die Verwendung von Enumerationen hat folgende Vorteile:  
  
-   Reduzierung von Fehlern, die durch das Übertragen von Zahlen oder falsch eingegebene Zahlen verursacht werden  
  
-   Vereinfachen der nachträglichen Änderung von Werten  
  
-   Erhöhung der Lesbarkeit des Codes, sodass sich weniger Fehler einschleichen können  
  
-   Sicherstellung der Vorwärtskompatibilität.  Mit Enumerationen wird das Auftreten von Fehlern im Code verringert, wenn die Werte, die den Membernamen entsprechen, nachträglich geändert werden.  
  
## Benennen von Enumerationen  
 Verwenden Sie eine Namenskonvention für Enumerationsmember.  Wenn [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] einen Enumerationsmembernamen erkennt, wird u. U. eine Ausnahme ausgelöst, falls andere Typbibliotheken, auf die verwiesen wird, denselben Namen enthalten.  Verwenden Sie ein eindeutiges Präfix zur Kennzeichnung der Werte Ihrer Anwendung oder Komponente.  
  
 Wenn Sie auf einen Member einer Enumeration verweisen, müssen Sie den Membernamen mit dem Enumerationsnamen qualifizieren oder die `Imports`\-Anweisung verwenden.  Weitere Informationen hierzu finden Sie unter [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).  
  
## Vordefinierte Enumerationen  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] stellt eine Reihe vordefinierter Enumerationen bereit, z. B. `FirstDayOfWeek` und `MsgBoxResul`t, die die Erstellung von Code erleichtern.  Eine Liste dieser Enumerationen finden Sie unter [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).  
  
## Siehe auch  
 [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)   
 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)   
 [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)   
 [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)