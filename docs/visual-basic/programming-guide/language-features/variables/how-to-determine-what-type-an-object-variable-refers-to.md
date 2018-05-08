---
title: 'Gewusst wie: Bestimmen des Typs, auf den eine Objektvariable verweist (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 0dfd4ed87b65f536802ae71cbc3de41e1c4f83af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Gewusst wie: Bestimmen des Typs, auf den eine Objektvariable verweist (Visual Basic)
Eine Objektvariable enthält einen Zeiger auf Daten, die an anderer Stelle gespeichert werden. Der Typ der Daten kann während der Laufzeit ändern. Zu jedem Zeitpunkt können Sie die <xref:System.Type.GetTypeCode%2A> Methode, um den aktuellen Laufzeittyp festzulegen oder die [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) um zu ermitteln, ob der aktuelle Laufzeittyp mit einem angegebenen Typ kompatibel ist.  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>Um zu bestimmen, dass die genaue geben derzeit eine Objektvariable verweist auf  
  
1.  Rufen Sie die Objektvariable der <xref:System.Object.GetType%2A> Methode zum Abrufen einer <xref:System.Type?displayProperty=nameWithType> Objekt.  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  Auf der <xref:System.Type?displayProperty=nameWithType> Klasse, rufen Sie die freigegebene Methode <xref:System.Type.GetTypeCode%2A> zum Abrufen der <xref:System.TypeCode> Enumerationswert für den Typ des Objekts.  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     Sie können testen, die <xref:System.TypeCode> Enumerationswert für Enumerationsmember von Interesse, z. B. sind `Double`.  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>Um zu bestimmen, ob ein Objekt ist Variablentyp kompatibel mit einem angegebenen Typ  
  
-   Verwenden der `TypeOf` Operator in Kombination mit der [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) So testen Sie das Objekt mit einem `TypeOf`... `Is` Ausdruck.  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     Die `TypeOf`... `Is` Ausdruck gibt `True` Typ ist mit dem angegebenen Typ kompatibel, wenn der zur Laufzeit des Objekts.  
  
     Das Kriterium für die Kompatibilität hängt davon ab, ob der angegebene Typ eine Klasse, Struktur oder Schnittstelle ist. Im Allgemeinen sind die Typen kompatibel, wenn das Objekt des gleichen Typs als ist, erbt oder den angegebenen Typ implementiert. Weitere Informationen finden Sie unter [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Beachten Sie, dass der angegebene Typ eine Variable oder ein Ausdruck sein kann. Es muss der Name eines definierten Typs, z. B. eine Klasse, Struktur oder Schnittstelle sein. Dazu gehören auch die systeminterne Typen `Integer` und `String`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.GetTypeCode%2A>  
 <xref:System.TypeCode>  
 [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)
