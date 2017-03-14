---
title: "How to: Declare and Call a Default Property in Visual Basic | Microsoft Docs"
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
  - "defaults, properties"
  - "properties [Visual Basic], default"
  - "procedures, defining"
  - "default properties, in Visual Basic"
  - "Visual Basic code, procedures"
  - "Visual Basic code, properties"
  - "default properties"
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# How to: Declare and Call a Default Property in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine *Standardeigenschaft* ist eine Klassen\- oder Struktureigenschaft, auf die der Code zugreifen kann, ohne dass die Eigenschaft angegeben wird.  Wenn der Aufrufcode eine Klasse oder Struktur, nicht jedoch eine Eigenschaft angibt und der Kontext den Zugriff auf eine Eigenschaft zulässt, löst [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] den Zugriff in die Standardeigenschaft dieser Klasse oder Struktur auf, falls eine solche Eigenschaft vorhanden ist.  
  
 Eine Klasse oder Struktur kann höchstens eine Standardeigenschaft haben.  Sie können eine Standardeigenschaft jedoch überladen und mehrere Versionen davon verwenden.  
  
 Weitere Informationen finden Sie unter [Default](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### So deklarieren Sie eine Standardeigenschaft  
  
1.  Deklarieren Sie die Eigenschaft auf die übliche Weise.  Geben Sie das `Shared`\-Schlüsselwort oder das `Private`\-Schlüsselwort nicht an.  
  
2.  Fügen Sie das `Default`\-Schlüsselwort in die Eigenschaftendeklaration ein.  
  
3.  Geben Sie mindestens einen Parameter für die Eigenschaft an.  Sie können keine Standardeigenschaft definieren, die nicht wenigstens ein Argument annimmt.  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### So rufen Sie eine Standardeigenschaft auf  
  
1.  Deklarieren Sie eine Variable der enthaltenden Klasse oder des Strukturtyps.  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  Verwenden Sie den Variablennamen allein in einem Ausdruck, in den Sie normalerweise den Eigenschaftennamen einfügen würden.  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  Geben Sie nach dem Variablennamen eine Argumentliste in runden Klammern ein.  Eine Standardeigenschaft muss mindestens ein Argument annehmen.  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  Um den Wert der Standardeigenschaft abzurufen, verwenden Sie den Variablennamen mit einer Argumentliste in einem Ausdruck oder nach dem Gleichheitszeichen \(`=`\) in einer Zuweisungsanweisung.  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  Um den Wert der Standardeigenschaft festzulegen, verwenden Sie den Variablennamen \(mit einer Argumentliste\) auf der linken Seite einer Zuweisungsanweisung.  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  Ebenso wie beim Zugriff auf andere Eigenschaften können Sie den Namen der Standardeigenschaft stets zusammen mit dem Variablennamen angeben.  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird eine Standardeigenschaft in einer Klasse deklariert.  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `myProperty`\-Standardeigenschaft in der `class1`\-Klasse aufgerufen wird.  Die drei Zuweisungsanweisungen speichern Werte in `myProperty`, und der <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>\-Aufruf liest die Werte.  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 Am häufigsten wird die <xref:Microsoft.VisualBasic.Collection.Item%2A>\-Eigenschaft in verschiedenen Auflistungsklassen als Standardeigenschaft verwendet.  
  
## Robuste Programmierung  
 Durch Standardeigenschaften wird zwar die Anzahl der Quellcodezeichen geringfügig verringert, der Code wird durch sie jedoch unter Umständen schlechter lesbar.  Wenn dem Aufrufcode die Klasse oder die Struktur, auf die verwiesen wird, nicht bekannt sind, ist unsicher, ob durch diesen Verweis auf die Klasse bzw. die Struktur selbst oder auf eine Standardeigenschaft zugegriffen wird.  Dies kann zu Compilerfehlern oder kleineren Laufzeitlogikfehlern führen.  
  
 Die Möglichkeit von Eigenschaftenfehlern lässt sich ein wenig reduzieren, wenn Sie stets die [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) verwenden, um die Compilertypüberprüfung auf `On` zu setzen.  
  
 Wenn Sie im Code eine vordefinierte Klasse oder Struktur verwenden möchten, müssen Sie festlegen, ob sie eine Standardeigenschaft besitzt. Ist dies der Fall, müssen Sie auch einen Namen für die Eigenschaft festlegen.  
  
 Aufgrund dieser Nachteile sollten Sie keine Standardeigenschaften definieren.  Zur besseren Lesbarkeit des Codes sollten Sie zudem stets explizit auf alle Eigenschaften verweisen, auch auf Standardeigenschaften.  
  
## Siehe auch  
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Default](../../../../visual-basic/language-reference/modifiers/default.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Declare a Property with Mixed Access Levels](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)