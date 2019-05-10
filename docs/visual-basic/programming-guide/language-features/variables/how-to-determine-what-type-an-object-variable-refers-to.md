---
title: 'Vorgehensweise: Bestimmen des Typs (Visual Basic) eine Objektvariable verweist'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 4ae73e6b3dec7864eb670bed67630b1cc96e5e61
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663552"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Vorgehensweise: Bestimmen des Typs (Visual Basic) eine Objektvariable verweist
Eine Objektvariable enthält einen Zeiger auf Daten, die an anderer Stelle gespeichert werden. Der Typ der Daten kann während der Laufzeit ändern. Sie können jederzeit eingehen, verwenden die <xref:System.Type.GetTypeCode%2A> Methode, um den aktuellen Laufzeittyp zu bestimmen oder die [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) um zu ermitteln, ob die aktuelle Laufzeit-Typinformationen mit einem angegebenen Typ kompatibel ist.  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>Bezieht sich auf, um zu bestimmen, dass genau eine Objektvariable derzeit eingeben  
  
1. Rufen Sie die Objektvariable, die <xref:System.Object.GetType%2A> Methode zum Abrufen einer <xref:System.Type?displayProperty=nameWithType> Objekt.  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2. Auf der <xref:System.Type?displayProperty=nameWithType> Klasse, rufen Sie die freigegebene Methode <xref:System.Type.GetTypeCode%2A> zum Abrufen der <xref:System.TypeCode> Enumerationswert für den Typ des Objekts.  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     Sie können testen, die <xref:System.TypeCode> Enumerationswert für Enumerationsmember von Interesse, z. B. sind `Double`.  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>Um zu bestimmen, ob ein Objekt ist Variablentyp kompatibel mit einem angegebenen Typ  
  
- Verwenden der `TypeOf` Operator in Kombination mit der [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) So testen Sie das Objekt mit einem `TypeOf`... `Is` Ausdruck.  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     Die `TypeOf`... `Is` gibt `True` Typ ist mit dem angegebenen Typ kompatibel, wenn der Laufzeit des Objekts.  
  
     Das Kriterium für die Kompatibilität hängt davon ab, ob der angegebene Typ eine Klasse, Struktur oder Schnittstelle ist. Im Allgemeinen sind die Typen kompatibel, wenn das Objekt vom gleichen Typ wie ist, erbt oder den angegebenen Typ implementiert. Weitere Informationen finden Sie unter [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Beachten Sie, dass der angegebene Typ eine Variable oder einen Ausdruck kann nicht an. Es muss den Namen eines definierten Typs, z. B. eine Klasse, Struktur oder Schnittstelle sein. Hierzu gehören z. B. systeminterne Typen `Integer` und `String`.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)
