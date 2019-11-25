---
title: Structure Statement
ms.date: 05/12/2018
f1_keywords:
- vb.Structure
- Structure
helpviewer_keywords:
- user-defined types [Visual Basic], Structure statement
- compound data types [Visual Basic]
- Structure keyword [Visual Basic]
- Structure statement [Visual Basic]
- UDT (user-defined types)
- types [Visual Basic], user-defined
ms.assetid: 9bd1deea-2a89-4cdc-812c-6dcbb947c391
ms.openlocfilehash: 120f836b9d49c00e9c53af0d1fc832e22c8cbbb8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346459"
---
# <a name="structure-statement"></a>Structure Statement

Deklariert den Namen einer Struktur und führt die Definitionen der Variablen, Eigenschaften, Ereignisse und Prozeduren ein, aus denen die Struktur besteht.

## <a name="syntax"></a>Syntax

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Partial ] _
Structure name [ ( Of typelist ) ]
    [ Implements interfacenames ]
    [ datamemberdeclarations ]
    [ methodmemberdeclarations ]
End Structure
```

## <a name="parts"></a>Teile

|Begriff|Definition|
|---|---|
|`attributelist`|Dies ist optional. See [Attribute List](attribute-list.md).|
|`accessmodifier`|Dies ist optional. Einer der folgenden Werte ist möglich:<br /><br /> -   [Public](../modifiers/public.md)<br />-   [Protected](../modifiers/protected.md)<br />-   [Friend](../modifiers/friend.md)<br />-   [Private](../modifiers/private.md)<br />- [Protected Friend](../modifiers/protected-friend.md)<br/>- [Private Protected](../modifiers/private-protected.md) <br /><br /> Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Dies ist optional. See [Shadows](../modifiers/shadows.md).|
|`Partial`|Dies ist optional. Gibt eine partielle Definition der Struktur an. See [Partial](../modifiers/partial.md).|
|`name`|Erforderlich. Name der Struktur. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`Of`|Dies ist optional. Gibt an, dass dies eine generische Struktur ist.|
|`typelist`|Required if you use the [Of](of-clause.md) keyword. Liste mit Typparametern für diese Struktur. See [Type List](type-list.md).|
|`Implements`|Dies ist optional. Gibt an, dass diese Struktur die Member einer oder mehrerer Schnittstellen implementiert. See [Implements Statement](implements-statement.md).|
|`interfacenames`|Erforderlich, wenn Sie die `Implements`-Anweisung verwenden. Die Namen der von dieser Struktur implementierten Schnittstellen.|
|`datamemberdeclarations`|Erforderlich. Zero or more `Const`, `Dim`, `Enum`, or `Event` statements declaring *data members* of the structure.|
|`methodmemberdeclarations`|Dies ist optional. Zero or more declarations of `Function`, `Operator`, `Property`, or `Sub` procedures, which serve as *method members* of the structure.|
|`End Structure`|Erforderlich. Beendet die `Structure`-Definition.|

## <a name="remarks"></a>Hinweise

Die `Structure`-Anweisung definiert einen zusammengesetzten Werttyp, den Sie anpassen können. A *structure* is a generalization of the user-defined type (UDT) of previous versions of Visual Basic. For more information, see [Structures](../../programming-guide/language-features/data-types/structures.md).

Strukturen unterstützen viele Funktionen, die auch von Klassen unterstützt werden. Strukturen können z. B. Eigenschaften und Prozeduren aufweisen, Schnittstellen implementieren und parametrisierte Konstruktoren enthalten. Allerdings bestehen zwischen Strukturen und Klassen erhebliche Unterschiede in den Bereichen Vererbung, Deklarationen und Verwendung. Außerdem sind Klassen Verweistypen, und Strukturen sind Werttypen. For more information, see [Structures and Classes](../../programming-guide/language-features/data-types/structures-and-classes.md).

`Structure` kann nur auf Namespace- oder Modulebene verwendet werden. This means the *declaration context* for a structure must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure or block. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).

Structures default to [Friend](../modifiers/friend.md) access. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

## <a name="rules"></a>Regeln

- **Nesting.** Sie können eine Struktur in einer anderen Struktur definieren. The outer structure is called the *containing structure*, and the inner structure is called a *nested structure*. Sie können jedoch nicht über die enthaltende Struktur auf die Member einer geschachtelten Struktur zugreifen. Stattdessen müssen Sie eine Variable mit dem Datentyp der geschachtelten Struktur deklarieren.

- **Member Declaration.** Sie müssen jeden Member einer Struktur deklarieren. A structure member cannot be [Protected](../modifiers/protected.md) or `Protected Friend` because nothing can inherit from a structure. Die Struktur selbst kann jedoch `Protected` oder `Protected Friend` sein.
  
     Sie können in einer Struktur null oder mehr nicht freigegebene Variablen oder nicht freigegebene nicht benutzerdefinierte Ereignisse deklarieren. Es ist nicht möglich, nur Konstanten, Eigenschaften und Prozeduren zu definieren, selbst wenn einige davon nicht gemeinsam genutzt werden.

- **Initialization.** Der Wert von nicht freigegebenen Datenmembern einer Struktur kann nicht als Teil der Deklaration initialisiert werden. Sie müssen einen solchen Datenmember entweder mit einem parametrisierten Konstruktor auf Strukturebene initialisieren oder dem Member nach dem Erstellen einer Instanz der Struktur einen Wert zuweisen.

- **Vererbung.** Eine Struktur kann von keinem anderen Typ als von <xref:System.ValueType> erben, von dem alle Strukturen erben. Insbesondere kann eine Struktur nicht von einer anderen Struktur erben.

     You cannot use the [Inherits Statement](inherits-statement.md) in a structure definition, even to specify <xref:System.ValueType>.

- **Implementation.** If the structure uses the [Implements Statement](implements-statement.md), you must implement every member defined by every interface you specify in `interfacenames`.

- **Default Property.** A structure can specify at most one property as its *default property*, using the [Default](../modifiers/default.md) modifier. For more information, see [Default](../modifiers/default.md).

## <a name="behavior"></a>Verhalten

- **Access Level.** In einer Struktur können Sie jeden Member mit einer eigenen Zugriffsebene deklarieren. All structure members default to [Public](../modifiers/public.md) access. Beachten Sie, dass der Zugriff auf die Member einer Struktur automatisch eingeschränkt ist, wenn die Struktur selbst über eine restriktivere Zugriffsebene verfügt, selbst wenn Sie die Zugriffsebenen der Member mit den Zugriffsmodifizierern anpassen.

- **Scope.** Der Gültigkeitsbereich einer Struktur umfasst den Namespace, die Klasse, Struktur oder das Modul, in dem bzw. der sich die Struktur befindet.

     Der Gültigkeitsbereich eines Strukturmembers umfasst die gesamte Struktur.

- **Lifetime.** Eine Struktur selbst verfügt nicht über eine Lebensdauer. Stattdessen verfügt jede Instanz der Struktur über eine Lebensdauer, die von allen anderen Instanzen unabhängig ist.

     The lifetime of an instance begins when it is created by a [New Operator](../operators/new-operator.md) clause. Sie endet, wenn die enthaltende Lebensdauer der Variablen endet.

     Sie können die Lebensdauer einer Strukturinstanz nicht verlängern. Eine den Funktionen einer statischen Struktur ähnelnde Funktionalität wird von einem Modul bereitgestellt. For more information, see [Module Statement](module-statement.md).

     Strukturmember verfügen über eine Lebensdauer, die davon abhängt, wie und wo sie deklariert werden. For more information, see "Lifetime" in [Class Statement](class-statement.md).

- **Qualification.** In Code außerhalb einer Struktur muss der Name eines Members mit dem Namen dieser Struktur qualifiziert werden.

     Wenn Code in einer geschachtelten Struktur einen nicht qualifizierten Verweis auf ein Programmierelement enthält, wird von Visual Basic das Element zunächst in der geschachtelten Struktur gesucht, anschließend in der enthaltenden Struktur und so weiter bis zum äußersten enthaltenden Element. Weitere Informationen finden Sie unter [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

- **Memory Consumption.** Wie bei allen zusammengesetzten Datentypen können Sie den gesamten Speicherverbrauch auch bei Strukturen nicht dadurch zuverlässig berechnen, indem Sie die nominalen Speicherbelegungen ihrer Member addieren. Darüber hinaus können Sie nicht davon ausgehen, dass die Member im Speicher in derselben Reihenfolge wie in der Deklaration angeordnet sind. Wenn Sie das Speicherlayout einer Struktur steuern müssen, können Sie das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut auf die `Structure`-Anweisung anwenden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die `Structure`-Anweisung für die Definition einer Gruppe verknüpfter Daten für einen Mitarbeiter verwendet. Es veranschaulicht die Verwendung von Membern mit dem Zugriff `Public`, `Friend` und `Private`, um den Grad der Vertraulichkeit der Datenelemente anzugeben. Es zeigt außerdem Prozedur-, Eigenschaften- und Ereignismember.

[!code-vb[VbVbalrStatements#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#57)]

For more information on how to use `Structure`s, see [Structure Variable](../../programming-guide/language-features/data-types/structure-variables.md).

## <a name="see-also"></a>Siehe auch

- [Class-Anweisung](class-statement.md)
- [Interface-Anweisung](interface-statement.md)
- [Module-Anweisung](module-statement.md)
- [Dim-Anweisung](dim-statement.md)
- [Const-Anweisung](const-statement.md)
- [Enum-Anweisung](enum-statement.md)
- [Event-Anweisung](event-statement.md)
- [Operator-Anweisung](operator-statement.md)
- [Property-Anweisung](property-statement.md)
- [Strukturen und Klassen](../../programming-guide/language-features/data-types/structures-and-classes.md)
