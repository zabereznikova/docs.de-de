---
title: "Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic) | Microsoft Docs"
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
  - "procedures, arguments"
  - "procedure arguments"
  - "arguments [Visual Basic], nonmodifiable"
  - "Visual Basic code, procedures"
  - "arguments [Visual Basic], modifiable"
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn Sie eine Prozedur aufrufen, übergeben Sie i. d. R. mindestens ein Argument an die Prozedur.  Jedes Argument entspricht einem zugrunde liegenden Programmierelement.  Sowohl die zugrunde liegenden Elemente als auch die Argumente selbst können veränderbar oder nicht veränderbar sein.  
  
## Veränderbare und nicht veränderbare Elemente  
 Ein Programmierelement kann entweder ein *veränderbares Element* sein, dessen Wert sich ändert, oder ein *nicht veränderbares Element*, dessen Wert fest bleibt, nachdem es erstellt wurde.  
  
 In der folgenden Tabelle werden veränderbare und nicht veränderbare Programmierelemente aufgeführt.  
  
|Veränderbare Elemente|Nicht veränderbare Elemente|  
|---------------------------|---------------------------------|  
|Lokale Variablen \(deklariert in Prozeduren\) einschließlich Objektvariablen, außer schreibgeschützten Variablen|Schreibgeschützte Variablen, Felder und Eigenschaften|  
|Felder \(Membervariablen von Modulen, Klassen und Strukturen\), außer schreibgeschützten Feldern|Konstanten und Literale|  
|Eigenschaften, außer schreibgeschützten Eigenschaften|Enumerationsmember|  
|Arrayelemente|Ausdrücke \(auch wenn deren Elemente veränderbar sind\)|  
  
## Veränderbare und nicht veränderbare Argumente  
 Einem *veränderbaren Argument* liegt ein veränderbares Element zugrunde.  Der Aufrufcode kann jederzeit einen neuen Wert speichern. Wenn eine [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)\-Übergabe des Arguments erfolgt, kann der Code in der Prozedur das zugrunde liegende Element im Aufrufcode ebenfalls ändern.  
  
 Einem *nicht veränderbaren Argument* liegt entweder ein nicht veränderbares Element zugrunde, oder es wird mit [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) übergeben.  Die Prozedur kann das zugrunde liegende Element im Aufrufcode nicht ändern, auch wenn es sich um ein veränderbares Element handelt.  Wenn es sich um ein nicht veränderbares Element handelt, kann es vom Aufrufcode selbst nicht geändert werden.  
  
 Die aufgerufene Prozedur ändert gegebenenfalls die Kopie eines nicht veränderbaren Arguments; die Änderung hat jedoch keinen Einfluss auf das im Aufrufcode zugrunde liegende Element.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [How to: Pass Arguments to a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Differences Between Passing an Argument By Value and By Reference](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [How to: Change the Value of a Procedure Argument](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [How to: Protect a Procedure Argument Against Value Changes](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [How to: Force an Argument to Be Passed by Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)