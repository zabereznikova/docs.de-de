---
title: "How to: Create a Property (Visual Basic) | Microsoft Docs"
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
  - "procedures, defining"
  - "Visual Basic code, procedures"
  - "Visual Basic code, properties"
  - "properties [Visual Basic]"
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Create a Property (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Eine Eigenschaftendefinition wird von einer `Property`\-Anweisung und einer `End Property`\-Anweisung eingeschlossen.  Innerhalb dieser Definition kann eine `Get`\-Prozedur, eine `Set`\-Prozedur oder beides definiert werden.  Der gesamte Code der Eigenschaft ist in diesen Prozeduren enthalten.  
  
 Die `Get`\-Prozedur ruft den Eigenschaftswert ab, während die `Set`\-Prozedur einen Wert speichert.  Wenn die Eigenschaft Lese\-\/Schreibzugriff haben soll, müssen Sie beide Prozeduren definieren.  Soll die Eigenschaft schreibgeschützt sein, definieren Sie nur `Get`. Soll die Eigenschaft lesegeschützt sein, definieren Sie nur `Set`.  
  
### So erstellen Sie eine Eigenschaft  
  
1.  Verwenden Sie außerhalb einer Eigenschaft oder Prozedur eine [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) und schließen Sie eine `End Property`\-Anweisung an.  
  
2.  Wenn die Eigenschaft Parameter annimmt, geben Sie nach dem `Property`\-Schlüsselwort den Namen der Prozedur und anschließend die Parameterliste in runden Klammern ein.  
  
3.  Geben Sie nach den Klammern eine `As`\-Klausel ein, um den Datentyp für den Eigenschaftswert anzugeben.  Der Datentyp muss auch bei einer lesegeschützten Eigenschaft angegeben werden.  
  
4.  Fügen Sie die erforderlichen `Get`\-Prozeduren und `Set`\-Prozeduren hinzu.  Anweisungen hierzu finden Sie im Folgenden.  
  
### So erstellen Sie eine Get\-Prozedur, die einen Eigenschaftswert abruft  
  
1.  Geben Sie zwischen der `Property`\-Anweisung und der `End Property`\-Anweisung eine [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md) ein, und schließen Sie eine `End Get`\-Anweisung an.  Für die `Get`\-Prozedur brauchen keine Parameter definiert zu werden.  
  
2.  Fügen Sie die Codeanweisungen ein, um den Eigenschaftswert zwischen der `Get`\-Anweisung und der `End Get`\-Anweisung abzurufen.  Dieser Code kann neben der Generierung und der Rückgabe des Eigenschaftswerts weitere Berechnungen und Datenbearbeitungsschritte enthalten.  
  
3.  Geben Sie mit einer `Return`\-Anweisung den Eigenschaftswert an den Aufrufcode zurück.  
  
 Für eine Schreib\-Lese\-Eigenschaft und eine schreibgeschützte Eigenschaft müssen Sie eine `Get`\-Prozedur schreiben.  Für eine lesegeschützte Eigenschaft dürfen Sie keine `Get`\-Prozedur definieren.  
  
### So erstellen Sie eine Set\-Prozedur, die einen Eigenschaftswert schreibt  
  
1.  Geben Sie zwischen der `Property`\-Anweisung und der `End Property`\-Anweisung eine [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md) ein, und schließen Sie eine `End Set`\-Anweisung an.  
  
2.  Geben Sie in der `Set`\-Anweisung nach dem `Set`\-Schlüsselwort eine Parameterliste in Klammern ein.  Diese Parameterliste muss wenigstens einen Wertparameter für den Wert enthalten, der vom Aufrufcode übergeben wird.  Der Standardname für diesen Wertparameter ist `Value`. Sie können jedoch gegebenenfalls einen anderen Namen verwenden.  Der Wertparameter muss zum gleichen Datentyp gehören wie die Eigenschaft selbst.  
  
3.  Fügen Sie die Codeanweisungen, mit denen in der Eigenschaft ein Wert gespeichert wird, zwischen die `Set`\-Anweisung und die `End Set`\-Anweisung ein.  Dieser Code kann neben Schritten zur Überprüfung und Speicherung des Eigenschaftswerts weitere Berechnungen und Datenbearbeitungsschritte enthalten.  
  
4.  Bestätigen Sie den vom Aufrufcode bereitgestellten Wert mit dem Wertparameter.  Sie können diesen Wert entweder direkt in einer Zuweisungsanweisung speichern oder ihn in einem Ausdruck verwenden, um den internen zu speichernden Wert zu berechnen.  
  
 Für eine Schreib\-Lese\-Eigenschaft und eine lesegeschützte Eigenschaft müssen Sie eine `Set`\-Prozedur schreiben.  Für eine schreibgeschützte Eigenschaft dürfen Sie keine `Set`\-Prozedur definieren.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Lese\-Schreib\-Eigenschaft erstellt, die einen vollständigen Namen in Form zweier konstituierender Namen speichert, als Vorname und Nachname.  Wenn der Aufrufcode `fullName` liest, kombiniert die `Get`\-Prozedur die beiden konstituierenden Namen und gibt den vollständigen Namen zurück.  Wenn der Aufrufcode einen neuen vollständigen Namen zuweist, versucht die `Set`\-Prozedur, den Namen in zwei konstituierende Namen aufzulösen.  Wird kein Leerzeichen gefunden, wird der gesamte Name als Vorname gespeichert.  
  
 [!code-vb[VbVbcnProcedures#8](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-create-a-property_1.vb)]  
  
 Im folgenden Beispiel werden typische Aufrufe der Eigenschaftenprozeduren von `fullName` dargestellt.  Mit dem ersten Aufruf wird der Eigenschaftswert festgelegt, mit dem zweiten Aufruf wird der Wert abgerufen.  
  
 [!code-vb[VbVbcnProcedures#9](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/how-to-create-a-property_2.vb)]  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)