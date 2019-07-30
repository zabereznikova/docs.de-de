---
title: 'Vorgehensweise: Bestimmen des Typs, auf den eine Objekt Variable verweist (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 935623dd4b6edca188f932aca0e560130199e8f6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626571"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Vorgehensweise: Bestimmen des Typs, auf den eine Objekt Variable verweist (Visual Basic)

Eine Objekt Variable enthält einen Zeiger auf Daten, die an anderer Stelle gespeichert werden. Der Typ der Daten, die während der Laufzeit geändert werden können. Sie können jederzeit die <xref:System.Type.GetTypeCode%2A> -Methode verwenden, um den aktuellen Lauf Zeittyp zu bestimmen, oder den [typeof-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) , um herauszufinden, ob der aktuelle Lauf Zeittyp mit einem angegebenen Typ kompatibel ist.

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>So bestimmen Sie den genauen Typ, auf den eine Objekt Variable zurzeit verweist

1. Rufen Sie die <xref:System.Object.GetType%2A> -Methode für die-Objekt Variable auf <xref:System.Type?displayProperty=nameWithType> , um ein-Objekt abzurufen.

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. Rufen Sie <xref:System.Type?displayProperty=nameWithType> in der-Klasse die Shared <xref:System.Type.GetTypeCode%2A> -Methode auf <xref:System.TypeCode> , um den-Enumerationswert für den Objekttyp abzurufen.

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    Sie können den Enumerationswert mit den <xref:System.TypeCode> von Ihnen relevanten Enumerationsmembern testen, `Double`z. b.

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>So bestimmen Sie, ob der Typ einer Objektvariablen mit einem angegebenen Typ kompatibel ist

- Verwenden Sie `TypeOf` den-Operator in Kombination mit dem [is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md) , um `TypeOf`das Objekt mit einem... `Is` Ausdruck.

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    Die `TypeOf`... der Ausdruck `True` gibt zurück, wenn der Lauf Zeittyp des Objekts mit dem angegebenen Typ kompatibel ist. `Is`

    Das Kriterium für die Kompatibilität hängt davon ab, ob der angegebene Typ eine Klasse, eine Struktur oder eine Schnittstelle ist. Im Allgemeinen sind die Typen kompatibel, wenn das Objekt vom gleichen Typ ist wie, erbt von oder implementiert den angegebenen Typ. Weitere Informationen finden Sie unter [typeof-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).

## <a name="compiling-the-code"></a>Kompilieren des Codes

Beachten Sie, dass der angegebene Typ keine Variable oder kein Ausdruck sein darf. Dabei muss es sich um den Namen eines definierten Typs handeln, z. b. eine Klasse, Struktur oder Schnittstelle. Dies schließt intrinsische Typen wie `Integer` und `String`ein.

## <a name="see-also"></a>Siehe auch

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)
