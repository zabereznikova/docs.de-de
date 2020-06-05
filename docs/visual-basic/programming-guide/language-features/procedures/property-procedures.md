---
title: Eigenschaftenprozeduren
ms.date: 07/20/2015
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
ms.openlocfilehash: cb5b0e12512e476b7c96bbfb19f8e4f470f6b498
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363732"
---
# <a name="property-procedures-visual-basic"></a>Eigenschaftenprozeduren (Visual Basic)

Eine Eigenschaften Prozedur ist eine Reihe von Visual Basic-Anweisungen, die eine benutzerdefinierte Eigenschaft für ein Modul, eine Klasse oder eine Struktur bearbeiten. Eigenschaften Prozeduren werden auch als *Eigenschaftenaccessoren*bezeichnet.

Visual Basic bietet die folgenden Eigenschaften Prozeduren:

- Eine `Get` Prozedur gibt den Wert einer Eigenschaft zurück. Sie wird aufgerufen, wenn Sie in einem Ausdruck auf die-Eigenschaft zugreifen.
- Eine `Set` Prozedur legt eine Eigenschaft auf einen Wert fest, einschließlich eines Objekt Verweises. Sie wird aufgerufen, wenn Sie der-Eigenschaft einen Wert zuweisen.

In der Regel definieren Sie Eigenschafts Prozeduren mithilfe der `Get` -Anweisung und der-Anweisung in Paaren `Set` , aber Sie können jede Prozedur allein definieren, wenn die Eigenschaft schreibgeschützt ([Get-Anweisung](../../../language-reference/statements/get-statement.md)) oder schreibgeschützt ([Set-Anweisung](../../../language-reference/statements/set-statement.md)) ist.

Sie können die `Get` -und-Prozedur weglassen, `Set` Wenn Sie eine automatisch implementierte Eigenschaft verwenden. Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](./auto-implemented-properties.md).

Sie können Eigenschaften in Klassen, Strukturen und Modulen definieren. Eigenschaften sind `Public` standardmäßig, d. h., Sie können Sie von überall in Ihrer Anwendung aufrufen, die auf den Container der Eigenschaft zugreifen können.

Einen Vergleich von Eigenschaften und Variablen finden Sie [unter Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](differences-between-properties-and-variables.md).

## <a name="declaration-syntax"></a>Deklarations Syntax

Eine Eigenschaft selbst wird durch einen Codeblock definiert, der in der- [Eigenschafts Anweisung](../../../language-reference/statements/property-statement.md) und der-Anweisung eingeschlossen ist `End Property` . Innerhalb dieses Blocks wird jede Eigenschaften Prozedur als interner Block angezeigt, der in einer Deklarations Anweisung ( `Get` oder `Set` ) und der entsprechenden `End` Deklaration eingeschlossen ist.

Die Syntax zum Deklarieren einer Eigenschaft und ihrer Prozeduren lautet wie folgt:

```vb
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]
    [AccessLevel] Get
        ' Statements of the Get procedure.
        ' The following statement returns an expression as the property's value.
        Return Expression
    End Get
    [AccessLevel] Set[(ByVal NewValue As DataType)]
        ' Statements of the Set procedure.
        ' The following statement assigns newvalue as the property's value.
        LValue = NewValue
    End Set
End Property
' - or -
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]
```

Der `Modifiers` kann die Zugriffsebene und Informationen zum überschreiben, überschreiben, freigeben und shadoading angeben und ob die Eigenschaft schreibgeschützt oder schreibgeschützt ist. Der für `AccessLevel` die- `Get` oder- `Set` Prozedur kann eine beliebige Ebene sein, die restriktiver ist als die für die Eigenschaft selbst angegebene Zugriffsebene. Weitere Informationen finden Sie unter [Property-Anweisung](../../../language-reference/statements/property-statement.md).

### <a name="data-type"></a>Datentyp

Der Datentyp der Eigenschaft und die Prinzipal Zugriffsebene werden in der- `Property` Anweisung definiert, nicht in den-Eigenschaften Prozeduren. Eine Eigenschaft kann nur einen Datentyp aufweisen. Beispielsweise können Sie keine Eigenschaft zum Speichern eines Werts, `Decimal` sondern zum Abrufen eines `Double` Werts definieren.

### <a name="access-level"></a>Zugriffsebene

Sie können jedoch eine Prinzipal Zugriffsebene für eine Eigenschaft definieren und die Zugriffsebene in einer der Eigenschaften Prozeduren weiter einschränken. Beispielsweise können Sie eine Eigenschaft definieren `Public` und dann eine Prozedur definieren `Private Set` . Die `Get` Prozedur bleibt bestehen `Public` . Sie können die Zugriffsebene nur in einer der Prozeduren einer Eigenschaft ändern, und Sie können Sie nur restriktiver machen als die Prinzipal Zugriffsebene. Weitere Informationen finden Sie unter Gewusst [wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](how-to-declare-a-property-with-mixed-access-levels.md).

## <a name="parameter-declaration"></a>Parameter Deklaration

Sie deklarieren jeden Parameter auf dieselbe Weise wie bei [unter Prozeduren](sub-procedures.md), mit der Ausnahme, dass der Übergabe Mechanismus lauten muss `ByVal` .

Die Syntax für jeden Parameter in der Parameterliste lautet wie folgt:

```vb
[Optional] ByVal [ParamArray] parametername As datatype
```

Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben. Die Syntax zum Angeben eines Standardwerts lautet wie folgt:

```vb
Optional ByVal parametername As datatype = defaultvalue
```

## <a name="property-value"></a>Eigenschaftswert

In einer- `Get` Prozedur wird der Rückgabewert für den aufrufenden Ausdruck als Wert der-Eigenschaft bereitgestellt.

In einer- `Set` Prozedur wird der neue-Eigenschafts Wert an den-Parameter der- `Set` Anweisung übergeben. Wenn Sie explizit einen Parameter deklarieren, müssen Sie ihn mit dem gleichen Datentyp wie die-Eigenschaft deklarieren. Wenn Sie keinen Parameter deklarieren, verwendet der Compiler den impliziten-Parameter, `Value` um den neuen Wert darzustellen, der der Eigenschaft zugewiesen werden soll.

## <a name="calling-syntax"></a>Aufruf Syntax

Sie rufen eine Eigenschaften Prozedur implizit auf, indem Sie einen Verweis auf die-Eigenschaft erstellen. Sie verwenden den Namen der Eigenschaft auf die gleiche Weise wie den Namen einer Variablen, mit dem Unterschied, dass Sie Werte für alle nicht optionalen Argumente angeben müssen, und Sie müssen die Argumentliste in Klammern einschließen. Wenn keine Argumente angegeben werden, können Sie die Klammern optional weglassen.

Die Syntax für einen impliziten `Set` aufrufsvorgang lautet wie folgt:

```vb
propertyname[(argumentlist)] = expression
```

Die Syntax für einen impliziten `Get` aufrufsvorgang lautet wie folgt:

```vb
lvalue = propertyname[(argumentlist)]
Do While (propertyname[(argumentlist)] > expression)
```

### <a name="illustration-of-declaration-and-call"></a>Abbildung der Deklaration und des Aufruf

Die folgende Eigenschaft speichert einen vollständigen Namen als zwei konstituierende Namen, den Vornamen und den Nachnamen. Wenn der Aufruf Code liest `fullName` , `Get` kombiniert die Prozedur die beiden Namen der einzelnen Teile und gibt den vollständigen Namen zurück. Wenn der Aufruf Code einen neuen vollständigen Namen zuweist, `Set` versucht die Prozedur, Sie in zwei konstituierende Namen zu unterteilen. Wenn kein Leerzeichen gefunden wird, wird alles als Vorname gespeichert.

[!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]

Das folgende Beispiel zeigt typische Aufrufe der-Eigenschaften Prozeduren von `fullName` :

[!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweisen](index.md)
- [Function-Prozeduren](function-procedures.md)
- [Operatorprozeduren](operator-procedures.md)
- [Parameter und Argumente von Prozeduren](procedure-parameters-and-arguments.md)
- [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](differences-between-properties-and-variables.md)
- [Vorgehensweise: Erstellen einer Eigenschaft](how-to-create-a-property.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](how-to-call-a-property-procedure.md)
- [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Ablegen eines Werts in eine Eigenschaft](how-to-put-a-value-in-a-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](how-to-get-a-value-from-a-property.md)
