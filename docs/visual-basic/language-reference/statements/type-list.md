---
title: Type List
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: 7e22ad6e32ec13f081391e1d47a80df8b1e65063
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84412987"
---
# <a name="type-list-visual-basic"></a>Typenliste (Visual Basic)

Gibt die *Typparameter* für ein *generisches* Programmier Element an. Mehrere Parameter werden durch Kommas getrennt. Im folgenden finden Sie die Syntax für einen Typparameter.

## <a name="syntax"></a>Syntax

```vb
[genericmodifier] typename [ As constraintlist ]
```

## <a name="parts"></a>Bestandteile

|Begriff|Definition|
|---|---|
|`genericmodifier`|Dies ist optional. Kann nur in generischen Schnittstellen und Delegaten verwendet werden. Sie können einen typkovariant deklarieren, indem Sie das Schlüsselwort [out](../modifiers/out-generic-modifier.md) oder Kontra Variant mit dem [in](../modifiers/in-generic-modifier.md) -Schlüsselwort verwenden. Siehe [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).|
|`typename`|Erforderlich. Der Name des Typparameters. Dies ist ein Platzhalter, der durch einen definierten Typ ersetzt werden soll, der durch das entsprechende Typargument bereitgestellt wird.|
|`constraintlist`|Optional. Liste der Anforderungen, die den Datentyp einschränken, der für bereitgestellt werden kann `typename` . Wenn Sie mehrere Einschränkungen haben, schließen Sie Sie in geschweiften Klammern ( `{ }` ) ein, und trennen Sie Sie durch Kommas. Sie müssen die Einschränkungs Liste mit dem [As](as-clause.md) -Schlüsselwort einführen. Sie verwenden `As` nur einmal am Anfang der Liste.|

## <a name="remarks"></a>Bemerkungen

Jedes generische Programmier Element muss mindestens einen Typparameter annehmen. Ein Typparameter ist ein Platzhalter für einen bestimmten Typ (ein *konstruiertes Element*), das vom Client Code beim Erstellen einer Instanz des generischen Typs angegeben wird. Sie können eine generische Klasse, Struktur, Schnittstelle, Prozedur oder einen Delegaten definieren.

Weitere Informationen zum Definieren eines generischen Typs finden Sie unter [generische Typen in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md). Weitere Informationen zu Typparameter Namen finden Sie unter [deklarierte Element Namen](../../programming-guide/language-features/declared-elements/declared-element-names.md).

## <a name="rules"></a>Regeln

- **Klammern.** Wenn Sie eine Typparameter Liste angeben, müssen Sie Sie in Klammern einschließen, und Sie müssen die Liste mit dem [of](of-clause.md) -Schlüsselwort einführen. Sie verwenden `Of` nur einmal am Anfang der Liste.

- **Auflagen.** Eine Liste der *Einschränkungen* für einen Typparameter kann die folgenden Elemente in beliebiger Kombination enthalten:

  - Eine beliebige Anzahl von Schnittstellen. Der angegebene Typ muss jede Schnittstelle in dieser Liste implementieren.

  - Höchstens eine Klasse. Der angegebene Typ muss von dieser Klasse erben.

  - Das `New`-Schlüsselwort. Der angegebene Typ muss einen Parameter losen Konstruktor verfügbar machen, auf den der generische Typ zugreifen kann. Dies ist hilfreich, wenn Sie einen Typparameter durch eine oder mehrere Schnittstellen einschränken. Ein Typ, der Schnittstellen implementiert, macht nicht notwendigerweise einen Konstruktor verfügbar, und abhängig von der Zugriffsebene eines Konstruktors kann der Code innerhalb des generischen Typs möglicherweise nicht darauf zugreifen.

  - Entweder das- `Class` Schlüsselwort oder das- `Structure` Schlüsselwort. Das- `Class` Schlüsselwort Schränkt einen generischen Typparameter ein, um zu verlangen, dass jedes an es übergebenen Typargument ein Verweistyp ist, z. b. eine Zeichenfolge, ein Array oder ein Delegat oder ein Objekt, das aus einer Das- `Structure` Schlüsselwort Schränkt einen generischen Typparameter ein, sodass jedes an ihn übergebenen Typargument ein Werttyp sein muss, z. b. eine Struktur, eine Enumeration oder ein grundlegender Datentyp. Sie können nicht `Class` `Structure` gleichzeitig und in denselben einschließen `constraintlist` .

  Der angegebene Typ muss jede Anforderung erfüllen, die Sie in einschließen `constraintlist` .

  Einschränkungen für die einzelnen Typparameter sind unabhängig von Einschränkungen für andere Typparameter.

## <a name="behavior"></a>Verhalten

- **Ersetzung der Kompilierzeit.** Wenn Sie einen konstruierten Typ aus einem generischen Programmier Element erstellen, geben Sie einen definierten Typ für jeden Typparameter an. Der Visual Basic Compiler ersetzt den angegebenen Typ für jedes Vorkommen von `typename` innerhalb des generischen Elements.

- **Fehlende Einschränkungen.** Wenn Sie keine Einschränkungen für einen Typparameter angeben, ist der Code auf die Vorgänge und Member beschränkt, die vom [Objekt Datentyp](../data-types/object-data-type.md) für diesen Typparameter unterstützt werden.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine Gerüst Definition einer generischen Wörterbuch Klasse, einschließlich einer Skeleton-Funktion, um dem Wörterbuch einen neuen Eintrag hinzuzufügen.

[!code-vb[VbVbalrStatements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#3)]

## <a name="example"></a>Beispiel

Da `dictionary` generisch ist, kann der Code, der ihn verwendet, eine Vielzahl von Objekten daraus erstellen, die jeweils die gleiche Funktionalität aufweisen, aber auf einem anderen Datentyp agieren. Das folgende Beispiel zeigt eine Codezeile, die ein `dictionary` -Objekt mit `String` Einträgen und `Integer` Schlüsseln erstellt.

[!code-vb[VbVbalrStatements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#4)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die entsprechende Skelett Definition, die im vorherigen Beispiel generiert wurde.

[!code-vb[VbVbalrStatements#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#5)]

## <a name="see-also"></a>Weitere Informationen

- [Natürlich](of-clause.md)
- [New-Operator](../operators/new-operator.md)
- [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)
- [Object Data Type](../data-types/object-data-type.md)
- [Function-Anweisung](function-statement.md)
- [Structure Statement](structure-statement.md)
- [Sub-Anweisung](sub-statement.md)
- [Vorgehensweise: Verwenden einer generischen Klasse](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md)
- [Geben Sie in](../modifiers/in-generic-modifier.md)
- [Vorgenommen](../modifiers/out-generic-modifier.md)
