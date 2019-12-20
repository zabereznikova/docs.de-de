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
|`attributelist`|Optional. Siehe [Attribut Liste](attribute-list.md).|
|`accessmodifier`|Optional. Kann einen der folgenden Werte annehmen:<br /><br /> -   [Public](../modifiers/public.md)<br />-   [geschützt](../modifiers/protected.md)<br />-   [Friend](../modifiers/friend.md)<br />-   [Privat](../modifiers/private.md)<br />- [geschützter Freund](../modifiers/protected-friend.md)<br/>- [Privat geschützt](../modifiers/private-protected.md) <br /><br /> Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Optional. Siehe [Shadows](../modifiers/shadows.md).|
|`Partial`|Optional. Gibt eine partielle Definition der Struktur an. Siehe [partielle](../modifiers/partial.md).|
|`name`|Erforderlich. Name der Struktur. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`Of`|Optional. Gibt an, dass dies eine generische Struktur ist.|
|`typelist`|Erforderlich, wenn Sie das [of](of-clause.md) -Schlüsselwort verwenden. Liste mit Typparametern für diese Struktur. Siehe [Typliste](type-list.md).|
|`Implements`|Optional. Gibt an, dass diese Struktur die Member einer oder mehrerer Schnittstellen implementiert. Siehe [implementierende Anweisung](implements-statement.md).|
|`interfacenames`|Erforderlich, wenn Sie die `Implements`-Anweisung verwenden. Die Namen der von dieser Struktur implementierten Schnittstellen.|
|`datamemberdeclarations`|Erforderlich. NULL oder mehr `Const`-, `Dim`-, `Enum`-oder `Event`-Anweisungen, die *Datenmember* der Struktur deklarieren.|
|`methodmemberdeclarations`|Optional. NULL oder mehr Deklarationen von `Function`-, `Operator`-, `Property`-oder `Sub`-Prozeduren, die als *Methodenmember* der Struktur fungieren.|
|`End Structure`|Erforderlich. Beendet die `Structure`-Definition.|

## <a name="remarks"></a>Hinweise

Die `Structure`-Anweisung definiert einen zusammengesetzten Werttyp, den Sie anpassen können. Eine *Struktur* ist eine Generalisierung des benutzerdefinierten Typs (User-Defined Type, UDT) früherer Versionen von Visual Basic. Weitere Informationen finden Sie unter [Strukturen](../../programming-guide/language-features/data-types/structures.md).

Strukturen unterstützen viele Funktionen, die auch von Klassen unterstützt werden. Strukturen können z. B. Eigenschaften und Prozeduren aufweisen, Schnittstellen implementieren und parametrisierte Konstruktoren enthalten. Allerdings bestehen zwischen Strukturen und Klassen erhebliche Unterschiede in den Bereichen Vererbung, Deklarationen und Verwendung. Außerdem sind Klassen Verweistypen, und Strukturen sind Werttypen. Weitere Informationen finden Sie unter [Strukturen und Klassen](../../programming-guide/language-features/data-types/structures-and-classes.md).

`Structure` kann nur auf Namespace- oder Modulebene verwendet werden. Dies bedeutet, dass der *Deklarations Kontext* für eine Struktur eine Quelldatei, ein Namespace, eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein muss und keine Prozedur oder kein Block sein kann. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).

Strukturen sind standardmäßig [Friend](../modifiers/friend.md) -Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

## <a name="rules"></a>Regeln

- **Tigste.** Sie können eine Struktur in einer anderen Struktur definieren. Die äußere Struktur wird als *enthaltende Struktur*bezeichnet, und die innere Struktur wird als geschachtelte *Struktur*bezeichnet. Sie können jedoch nicht über die enthaltende Struktur auf die Member einer geschachtelten Struktur zugreifen. Stattdessen müssen Sie eine Variable mit dem Datentyp der geschachtelten Struktur deklarieren.

- **Member-Deklaration.** Sie müssen jeden Member einer Struktur deklarieren. Ein Strukturmember kann nicht [geschützt](../modifiers/protected.md) oder `Protected Friend` werden, da nichts von einer Struktur erben kann. Die Struktur selbst kann jedoch `Protected` oder `Protected Friend` sein.
  
     Sie können in einer Struktur null oder mehr nicht freigegebene Variablen oder nicht freigegebene nicht benutzerdefinierte Ereignisse deklarieren. Es ist nicht möglich, nur Konstanten, Eigenschaften und Prozeduren zu definieren, selbst wenn einige davon nicht gemeinsam genutzt werden.

- **Initialisierung.** Der Wert von nicht freigegebenen Datenmembern einer Struktur kann nicht als Teil der Deklaration initialisiert werden. Sie müssen einen solchen Datenmember entweder mit einem parametrisierten Konstruktor auf Strukturebene initialisieren oder dem Member nach dem Erstellen einer Instanz der Struktur einen Wert zuweisen.

- **Vererbung.** Eine Struktur kann von keinem anderen Typ als von <xref:System.ValueType> erben, von dem alle Strukturen erben. Insbesondere kann eine Struktur nicht von einer anderen Struktur erben.

     Die [erbt-Anweisung](inherits-statement.md) kann nicht in einer Struktur Definition verwendet werden, auch um <xref:System.ValueType>anzugeben.

- **Ausführungs.** Wenn die-Struktur die [implementierte Anweisung](implements-statement.md)verwendet, müssen Sie jeden Member implementieren, der von jeder Schnittstelle definiert wird, die Sie in `interfacenames`angeben.

- **Standard Eigenschaft.** Eine-Struktur kann höchstens eine Eigenschaft als *Standard Eigenschaft*angeben, wobei der [Standardmodifizierer](../modifiers/default.md) verwendet wird. Weitere Informationen finden Sie unter [default (Standard](../modifiers/default.md)).

## <a name="behavior"></a>Verhalten

- **Zugriffsebene.** In einer Struktur können Sie jeden Member mit einer eigenen Zugriffsebene deklarieren. Alle Strukturmember haben standardmäßig den [öffentlichen](../modifiers/public.md) Zugriff. Beachten Sie, dass der Zugriff auf die Member einer Struktur automatisch eingeschränkt ist, wenn die Struktur selbst über eine restriktivere Zugriffsebene verfügt, selbst wenn Sie die Zugriffsebenen der Member mit den Zugriffsmodifizierern anpassen.

- **Umfang.** Der Gültigkeitsbereich einer Struktur umfasst den Namespace, die Klasse, Struktur oder das Modul, in dem bzw. der sich die Struktur befindet.

     Der Gültigkeitsbereich eines Strukturmembers umfasst die gesamte Struktur.

- **Amtszeit.** Eine Struktur selbst verfügt nicht über eine Lebensdauer. Stattdessen verfügt jede Instanz der Struktur über eine Lebensdauer, die von allen anderen Instanzen unabhängig ist.

     Die Lebensdauer einer Instanz beginnt, wenn Sie von einer [neuen Operator](../operators/new-operator.md) Klausel erstellt wird. Sie endet, wenn die enthaltende Lebensdauer der Variablen endet.

     Sie können die Lebensdauer einer Strukturinstanz nicht verlängern. Eine den Funktionen einer statischen Struktur ähnelnde Funktionalität wird von einem Modul bereitgestellt. Weitere Informationen finden Sie unter [Modul Anweisung](module-statement.md).

     Strukturmember verfügen über eine Lebensdauer, die davon abhängt, wie und wo sie deklariert werden. Weitere Informationen finden Sie unter "Lebensdauer" in [Class-Anweisung](class-statement.md).

- **Abschluss.** In Code außerhalb einer Struktur muss der Name eines Members mit dem Namen dieser Struktur qualifiziert werden.

     Wenn Code in einer geschachtelten Struktur einen nicht qualifizierten Verweis auf ein Programmierelement enthält, wird von Visual Basic das Element zunächst in der geschachtelten Struktur gesucht, anschließend in der enthaltenden Struktur und so weiter bis zum äußersten enthaltenden Element. Weitere Informationen finden Sie unter [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

- **Arbeitsspeicher Nutzung.** Wie bei allen zusammengesetzten Datentypen können Sie den gesamten Speicherverbrauch auch bei Strukturen nicht dadurch zuverlässig berechnen, indem Sie die nominalen Speicherbelegungen ihrer Member addieren. Darüber hinaus können Sie nicht davon ausgehen, dass die Member im Speicher in derselben Reihenfolge wie in der Deklaration angeordnet sind. Wenn Sie das Speicherlayout einer Struktur steuern müssen, können Sie das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut auf die `Structure`-Anweisung anwenden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die `Structure`-Anweisung für die Definition einer Gruppe verknüpfter Daten für einen Mitarbeiter verwendet. Es veranschaulicht die Verwendung von Membern mit dem Zugriff `Public`, `Friend` und `Private`, um den Grad der Vertraulichkeit der Datenelemente anzugeben. Es zeigt außerdem Prozedur-, Eigenschaften- und Ereignismember.

[!code-vb[VbVbalrStatements#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#57)]

Weitere Informationen zur Verwendung von `Structure`s finden Sie unter [Struktur Variable](../../programming-guide/language-features/data-types/structure-variables.md).

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
