---
title: Objekt-Werte (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- object variables, values
- values, of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ff219571de9c76802d3f8d3046cf6b6f9d5be9d5
ms.lasthandoff: 03/13/2017

---
# <a name="object-variable-values-visual-basic"></a>Werte von Objektvariablen (Visual Basic)
Eine Variable, der die [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md) kann auf Daten eines beliebigen Typs verweisen. Der Wert in einer `Object` Variable wird an anderer Stelle im Arbeitsspeicher beibehalten, während die Variable selbst ein Zeiger auf die Daten enthält.  
  
## <a name="object-classifier-functions"></a>Objekt-Klassifizierungsfunktionen  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]enthält Funktionen, Zurückgeben von Informationen darüber, was, eine `Object` Variable verweist auf, wie in der folgenden Tabelle dargestellt.  
  
|Funktion|Gibt True zurück, wenn auf die Objektvariable verweist|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A></xref:Microsoft.VisualBasic.Information.IsArray%2A>|Ein Array von Werten, keinen einzelnen Wert|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A></xref:Microsoft.VisualBasic.Information.IsDate%2A>|Ein [Date-Datentyp](../../../../visual-basic/language-reference/data-types/date-data-type.md) Wert oder eine Zeichenfolge, die als Wert für Datum und Uhrzeit interpretiert werden kann|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A></xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Ein Objekt vom Typ <xref:System.DBNull>der fehlende oder nicht vorhandene Daten darstellt</xref:System.DBNull>|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A></xref:Microsoft.VisualBasic.Information.IsError%2A>|Ein Exception-Objekt, die von abgeleitet wird<xref:System.Exception></xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A></xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Nichts](../../../../visual-basic/language-reference/nothing.md), dass der Variablen gegenwärtig kein Objekt zugewiesen ist|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A></xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Eine Zahl oder eine Zeichenfolge, die als Zahl interpretiert werden kann|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A></xref:Microsoft.VisualBasic.Information.IsReference%2A>|Ein Verweistyp (z. B. eine Zeichenfolge, ein Array, Delegat oder ein Klassentyp)|  
  
 Diese Funktionen können Sie vermeiden, senden einen ungültigen Wert für einen Vorgang oder eine Prozedur.  
  
## <a name="typeof-operator"></a>Operator TypeOf  
 Sie können auch die [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) zu bestimmen, ob eine Objektvariable gegenwärtig auf einen bestimmten Datentyp verweist. The `TypeOf`... `Is` Ausdruck ergibt `True` , wenn der Laufzeittyp des Operanden abgeleitet ist oder den angegebenen Typ implementiert.  
  
 Im folgenden Beispiel wird `TypeOf` auf Objektvariablen, die auf Wert-und Verweistypen verweisen.  
  
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
  
 Das vorhergehende Beispiel schreibt die folgenden Zeilen der **Debuggen** Fenster:  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 Die Objektvariable `num` bezieht sich auf Daten des Typs `Integer`, und `frm` bezieht sich auf ein Objekt der Klasse <xref:System.Windows.Forms.Form>.</xref:System.Windows.Forms.Form>  
  
## <a name="object-arrays"></a>Objektarrays  
 Sie können deklarieren und verwenden Sie ein Array von `Object` Variablen. Dies ist hilfreich, wenn Sie eine Vielzahl von Datentypen und Objektklassen verarbeiten müssen. Alle Elemente in einem Array müssen den gleichen Datentyp deklariert. Dieser Datentyp als deklarieren `Object` ermöglicht es Ihnen, Objekte zu speichern und Klasseninstanzen neben weiteren Datentypen im Array.  
  
## <a name="see-also"></a>Siehe auch  
 [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Zuweisen von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Gewusst wie: Verweisen auf die aktuelle Instanz eines Objekts](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)   
 [Gewusst wie: Bestimmen des Typs, auf den eine Objektvariable verweist](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)   
 [Gewusst wie: Bestimmen des Bezugs zwischen zwei Objekten](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [Gewusst wie: bestimmen, ob zwei Objekte identisch sind](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)   
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
