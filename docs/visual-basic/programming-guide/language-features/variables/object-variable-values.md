---
title: Werte von Objektvariablen
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: 800b9754ce27cc6a494dd781d06f4bdca8a10e87
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91080230"
---
# <a name="object-variable-values-visual-basic"></a>Werte von Objektvariablen (Visual Basic)

Eine Variable des [Objekt Datentyps](../../../language-reference/data-types/object-data-type.md) kann auf Daten eines beliebigen Typs verweisen. Der Wert, den Sie in einer `Object` Variablen speichern, wird an anderer Stelle im Arbeitsspeicher beibehalten, während die Variable selbst einen Zeiger auf die Daten enthält.  
  
## <a name="object-classifier-functions"></a>Objektklassifizierungs Funktionen  

 Visual Basic stellt Funktionen bereit, die Informationen über das, `Object` auf die eine Variable verweist, zurückgeben, wie in der folgenden Tabelle dargestellt.  
  
|Funktion|Gibt true zurück, wenn die Objekt Variable auf verweist.|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|Ein Array von Werten anstelle eines einzelnen Werts|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|Ein [Date-Datentyp](../../../language-reference/data-types/date-data-type.md) Wert oder eine Zeichenfolge, die als Datums-und Uhrzeitwert interpretiert werden kann.|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Ein Objekt vom Typ <xref:System.DBNull> , das fehlende oder nicht vorhandene Daten darstellt.|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|Ein Ausnahme Objekt, das von abgeleitet ist. <xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Nothing](../../../language-reference/nothing.md), das heißt, es ist zurzeit kein Objekt der Variablen zugewiesen.|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Eine Zahl oder eine Zeichenfolge, die als Zahl interpretiert werden kann.|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|Ein Verweistyp (z. b. eine Zeichenfolge, ein Array, ein Delegat oder ein Klassentyp)|  
  
 Sie können diese Funktionen verwenden, um zu vermeiden, dass ein ungültiger Wert an einen Vorgang oder eine Prozedur gesendet wird.  
  
## <a name="typeof-operator"></a>Operator TypeOf  

 Sie können auch den [typeof-Operator](../../../language-reference/operators/typeof-operator.md) verwenden, um zu bestimmen, ob eine Objekt Variable derzeit auf einen bestimmten Datentyp verweist. Der `TypeOf` Ausdruck... `Is` wird als ausgewertet, `True` Wenn der Lauf Zeittyp des Operanden von abgeleitet ist oder den angegebenen Typ implementiert.  
  
 Im folgenden Beispiel wird `TypeOf` für Objektvariablen verwendet, die auf Wert-und Verweis Typen verweisen.  
  
```vb  
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
  
 Im vorherigen Beispiel werden die folgenden Zeilen in das **Debugfenster** geschrieben:  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 Die Objekt Variable `num` verweist auf Daten vom Typ `Integer` und `frm` verweist auf ein Objekt der Klasse <xref:System.Windows.Forms.Form> .  
  
## <a name="object-arrays"></a>Objekt Arrays  

 Sie können ein Array von Variablen deklarieren und verwenden `Object` . Dies ist nützlich, wenn Sie eine Vielzahl von Datentypen und Objektklassen verarbeiten müssen. Alle Elemente in einem Array müssen denselben deklarierten Datentyp aufweisen. Durch das Deklarieren dieses Datentyps als `Object` können Sie Objekte und Klassen Instanzen neben anderen Datentypen im Array speichern.  
  
## <a name="see-also"></a>Siehe auch

- [Objektvariablen](object-variables.md)
- [Deklaration von Objektvariablen](object-variable-declaration.md)
- [Zuweisung von Objektvariablen](object-variable-assignment.md)
- [Vorgehensweise: Verweisen auf die aktuelle Instanz eines Objekts](how-to-refer-to-the-current-instance-of-an-object.md)
- [Vorgehensweise: Bestimmen des Typs, auf den eine Objektvariable verweist](how-to-determine-what-type-an-object-variable-refers-to.md)
- [Vorgehensweise: Bestimmen des Bezugs zwischen zwei Objekten](how-to-determine-whether-two-objects-are-related.md)
- [Vorgehensweise: Bestimmen der Gleichheit zweier Objekte](how-to-determine-whether-two-objects-are-identical.md)
- [Datentypen](../data-types/index.md)
