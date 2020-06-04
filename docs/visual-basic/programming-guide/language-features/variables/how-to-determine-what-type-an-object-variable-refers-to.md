---
title: 'Vorgehensweise: Bestimmen des Typs, auf den eine Objektvariable verweist'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: d3224000f5958a8619e38c4d2f6dc5dbb275ad45
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410489"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Gewusst wie: Bestimmen des Typs, auf den eine Objektvariable verweist (Visual Basic)

Eine Objekt Variable enthält einen Zeiger auf Daten, die an anderer Stelle gespeichert werden. Der Typ der Daten, die während der Laufzeit geändert werden können. Sie können jederzeit die-Methode verwenden, <xref:System.Type.GetTypeCode%2A> um den aktuellen Lauf Zeittyp zu bestimmen, oder den [typeof-Operator](../../../language-reference/operators/typeof-operator.md) , um herauszufinden, ob der aktuelle Lauf Zeittyp mit einem angegebenen Typ kompatibel ist.

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>So bestimmen Sie den genauen Typ, auf den eine Objekt Variable zurzeit verweist

1. Rufen Sie die-Methode für die-Objekt Variable auf, <xref:System.Object.GetType%2A> um ein- <xref:System.Type?displayProperty=nameWithType> Objekt abzurufen.

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. Rufen Sie in der- <xref:System.Type?displayProperty=nameWithType> Klasse die Shared-Methode auf, <xref:System.Type.GetTypeCode%2A> um den <xref:System.TypeCode> -Enumerationswert für den Objekttyp abzurufen.

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    Sie können den <xref:System.TypeCode> Enumerationswert mit den von Ihnen relevanten Enumerationsmembern testen, z `Double` . b..

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>So bestimmen Sie, ob der Typ einer Objektvariablen mit einem angegebenen Typ kompatibel ist

- Verwenden Sie den- `TypeOf` Operator in Kombination mit dem [is-Operator](../../../language-reference/operators/is-operator.md) , um das Objekt mit einem `TypeOf` ...-Ausdruck zu testen `Is` .

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    Der `TypeOf` ... `Is` -Ausdruck gibt zurück, `True` Wenn der Lauf Zeittyp des Objekts mit dem angegebenen Typ kompatibel ist.

    Das Kriterium für die Kompatibilität hängt davon ab, ob der angegebene Typ eine Klasse, eine Struktur oder eine Schnittstelle ist. Im Allgemeinen sind die Typen kompatibel, wenn das Objekt vom gleichen Typ ist wie, erbt von oder implementiert den angegebenen Typ. Weitere Informationen finden Sie unter [typeof-Operator](../../../language-reference/operators/typeof-operator.md).

## <a name="compile-the-code"></a>Kompilieren des Codes

Beachten Sie, dass der angegebene Typ keine Variable oder kein Ausdruck sein darf. Dabei muss es sich um den Namen eines definierten Typs handeln, z. b. eine Klasse, Struktur oder Schnittstelle. Dies schließt intrinsische Typen wie `Integer` und ein `String` .

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [Objektvariablen](object-variables.md)
- [Werte von Objektvariablen](object-variable-values.md)
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
