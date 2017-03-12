---
title: "Object Variable Values (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "object variables, values"
  - "values, of object variables"
  - "data types [Visual Basic], object variable"
  - "variables [Visual Basic], object"
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Object Variable Values (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Eine Variable vom Typ [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) kann auf Daten beliebigen Typs verweisen.  Der in einer `Object`\-Variablen gespeicherte Wert befindet sich an einer anderen Speicherposition als die Variable, die lediglich einen Zeiger auf diesen Wert enthält.  
  
## Funktionen zur Objektklassifizierung  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] enthält Funktionen, die Informationen über das Objekt zurückgeben, auf das eine `Object`\-Variable verweist \(siehe folgende Tabelle\).  
  
|Funktion|Gibt "True" zurück, wenn die Objektvariable auf Folgendes verweist|  
|--------------|------------------------------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|Ein Array von Werten, nicht einen einzelnen Wert|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|Ein [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md)\-Wert oder eine Zeichenfolge, die als Datums\- und Zeitwert interpretiert werden kann|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Ein Objekt des Typs <xref:System.DBNull>, der fehlende oder nicht vorhandene Daten darstellt|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|Ein Ausnahmeobjekt, das von <xref:System.Exception> abgeleitet ist|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Nothing](../../../../visual-basic/language-reference/nothing.md) bedeutet, dass der Variablen gegenwärtig kein Objekt zugewiesen ist.|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Eine Zahl oder eine Zeichenfolge, die als Zahl interpretiert werden kann|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|Ein Verweistyp \(z. B. eine Zeichenfolge, ein Array, Delegat oder Klassentyp\)|  
  
 Mit diesen Funktionen wird vermieden, dass ungültige Werte an Operationen oder Prozeduren gesendet werden.  
  
## Operator TypeOf  
 Mit dem [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) kann festgestellt werden, ob eine Objektvariable gegenwärtig auf einen bestimmten Datentyp verweist.  Die Auswertung des `TypeOf`...`Is`\-Ausdrucks ergibt `True`, wenn der Laufzeittyp des Operanden vom angegebenen Typ abgeleitet ist oder diesen implementiert.  
  
 Im folgenden Beispiel wird `TypeOf` auf Objektvariablen angewendet, die auf Wert\- und Verweistypen verweisen:  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 Im vorhergehenden Beispiel werden die folgenden Zeilen im Fenster **Debuggen** ausgegeben:  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 Die Objektvariable `num` verweist auf Daten des Typs `Integer`. `frm` verweist auf ein Objekt der Klasse <xref:System.Windows.Forms.Form>.  
  
## Objektarrays  
 Sie können ein Array von `Object`\-Variablen deklarieren und einsetzen.  Dies ist dann sinnvoll, wenn unterschiedliche Datentypen und Objektklassen verarbeitet werden müssen.  Alle Elemente in einem Array müssen mit dem gleichen Datentyp deklariert sein.  Wenn dieser Datentyp als `Object` deklariert wird, können Objekte und Klasseninstanzen neben weiteren Datentypen im Array gespeichert werden.  
  
## Siehe auch  
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [How to: Refer to the Current Instance of an Object](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)   
 [How to: Determine What Type an Object Variable Refers To](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)   
 [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [How to: Determine Whether Two Objects Are Identical](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)   
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)