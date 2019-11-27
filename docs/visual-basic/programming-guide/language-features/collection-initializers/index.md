---
title: Auflistungsinitialisierer
ms.date: 07/20/2015
f1_keywords:
- vb.CollectionInitializer
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: a9290329-77b0-4fdf-ae75-8fc17287f469
ms.openlocfilehash: fbdd116298c530ae54677631eff7dac2f22c0fe2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346779"
---
# <a name="collection-initializers-visual-basic"></a>Auflistungsinitialisierer (Visual Basic)

*Auflistungsinitialisierer* stellen eine gekürzte Syntax bereit, mit der Sie eine Auflistung erstellen und mit einem anfänglichen Satz von Werten auffüllen können. Auflistungsinitialisierer sind nützlich beim Erstellen einer Auflistung aus einem Satz unbekannter Werte, z.B. eine Liste von Menüoptionen oder Kategorien, ein ursprünglicher Satz numerischer Werte, eine statische Liste von Zeichenfolgen wie Tag- oder Monatsnamen oder geografische Orte, z.B. eine Liste von Staaten, die für eine Überprüfung verwendet werden.

Weitere Informationen über Auflistungen finden Sie unter [Auflistungen](../../../../visual-basic/programming-guide/concepts/collections.md).

Sie identifizieren einen Auflistungsinitialisierer durch Gebrauch des Schlüsselworts `From`, gefolgt von Klammern (`{}`). Dies hat eine Ähnlichkeit mit der Arrayliteralsyntax, die unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md) beschrieben ist. Die folgenden Beispiele stellen unterschiedliche Möglichkeiten für die Verwendung von Auflistungsinitialisierern für die Erstellung von Auflistungen dar.

[!code-vb[VbVbalrCollectionInitializers#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#1)]

> [!NOTE]
> C# stellt ebenso Auflistungsinitialisierer bereit. C#-Auflistungsinitialisierer bieten die gleichen Funktionen wie Visual Basic-Auflistungsinitialisierer. Informationen über C#-Auflistungsinitialisierer finden Sie unter [Objekt- und Auflistungsinitialisierer](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).

## <a name="syntax"></a>Syntax

Ein Auflistungsinitialisierer besteht aus einer Liste von durch Komma getrennte Werte, die in Klammern (`{}`) eingeschlossen sind. Das Schlüsselwort `From` ist vorangestellt, wie im folgenden Code dargestellt.

[!code-vb[VbVbalrCollectionInitializers#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#2)]

Wenn Sie eine Auflistung erstellen, z.B. <xref:System.Collections.Generic.List%601> oder <xref:System.Collections.Generic.Dictionary%602>, müssen Sie den Auflistungstyp vor dem Auflistungsinitialisierer angeben, so wie im folgenden Code dargestellt.

[!code-vb[VbVbalrCollectionInitializers#13](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#13)]

> [!NOTE]
> Sie können nicht einen Auflistungsinitialisierer und einen Objektinitialisierer kombinieren, um das gleiche Auflistungsobjekt zu initialisieren. Sie können Objektinitialisierer zum Initialisieren von Objekten in einem Auflistungsinitialisierer verwenden.

## <a name="creating-a-collection-by-using-a-collection-initializer"></a>Erstellen einer Sammlung mithilfe eines sammlungsinitialisierers

Wenn Sie eine Sammlung durch Verwendung eines Auflistunsinitialisierers erstellen, wird jeder Wert, der im Auflistunsinitialisierer angegeben ist, an die entsprechende `Add`-Methode der Auflistung übergeben. Wenn Sie z.B. eine <xref:System.Collections.Generic.List%601> durch Verwendung eines Auflistungsinitialisierers erstellen, wird jeder Zeichenfolgenwert im Auflistungsinitialisierer an die <xref:System.Collections.Generic.List%601.Add%2A>-Methode übergeben. Wenn Sie eine Auflistung mithilfe eines Auflistungsinitialisierers erstellen möchten, muss der angegebene Typ ein gültiger Auflistungstyp sein. Beispiele gültiger Auflistungstypen enthalten Klassen, die die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementieren oder die <xref:System.Collections.CollectionBase>-Klasse erben. Der angegebene Typ muss auch eine `Add`-Methode verfügbar machen, die die folgenden Kriterien erfüllt.

- Die `Add`-Methode muss aus dem Bereich verfügbar sein, aus dem der Auflistungsinitialisierer aufgerufen wird. Die `Add`-Methode muss öffentlich sein, wenn Sie den Auflistungsinitialisierer in einem Szenario verwenden, in dem auf nicht-öffentliche Methode der Auflistung zugegriffen werden kann.

- Die `Add`-Methode muss ein Instanzmember oder `Shared`-Member der Auflistungsklasse sein oder eine Erweiterungsmethode.

- Es muss eine `Add`-Methode existieren, die auf Basis von Regeln der Überladungsauflösung mit den Typen verglichen werden kann, die im Auflistungsinitialisierer bereitgestellt werden.

 Beispielsweise wird im folgenden Codebeispiel gezeigt, wie eine `List(Of Customer)`-Auflistung mithilfe eines Auflistungsinitialisierers erstellt wird. Wenn der Code ausgeführt wird, wird jedes `Customer`-Objekt an die `Add(Customer)`-Methode der generischen Liste übergeben.

[!code-vb[VbVbalrCollectionInitializers#9](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#9)]

Das folgende Codebeispiel zeigt gleichwertigen Code, der keinen Auflistungsinitialisierer verwendet.

[!code-vb[VbVbalrCollectionInitializers#10](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#10)]

Wenn die Auflistung über eine `Add`-Methode verfügt, die Parameter besitzt, die mit dem Konstruktor für das `Customer`-Objekt übereinstimmen, können Sie Parameterwerte für die `Add`-Methode innerhalb von Auflistungsinitialisierern schachteln, so wie im nächsten Abschnitt beschrieben. Wenn die Auflistung nicht über diese `Add`-Methode verfügt, können Sie eine als Erweiterungsmethode erstellen. Ein Beispiel, wie Sie eine `Add`-Methode als Sammlung für eine Auflistung erstellen, finden Sie unter [Vorgehensweise: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md). Ein Beispiel, wie Sie eine benutzerdefinierte Auflistung erstellen, die mit einem Auflistungsinitialisierer verwendet werden kann, finden Sie unter [Vorgehensweise: Erstellen einer Auflistung für einen Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md).

## <a name="nesting-collection-initializers"></a>Schachteln von Auflistungsinitialisierern

Sie können Werte innerhalb eines Auflistungsinitialisierers schachteln, um eine bestimmte Überladung einer `Add`-Methode für die Auflistung, die erstellt wird, zu identifizieren. Die Werte, die an die `Add`-Methode übergeben werden, müssen durch Kommas getrennt und in Klammern (`{}`) eingeschlossen werden, so wie Sie das auch in einem Arrayliteral oder Auflistungsinitialisierer tun würden.

Wenn Sie ein Auflistung mithilfe geschachtelter Werte erstellen, wird jedes Element der geschachtelten Werteliste an das Argument an die `Add`-Methode übergeben, die mit den Elementtypen übereinstimmt. Beispielsweise erstellt das folgende Codebeispiel eine <xref:System.Collections.Generic.Dictionary%602>, in der die Schlüssel vom Typ `Integer` und die Werte vom Typ `String` sind. Jede der geschachtelten Wertelisten wird mit der <xref:System.Collections.Generic.Dictionary%602.Add%2A>-Methode für `Dictionary` verglichen.

[!code-vb[VbVbalrCollectionInitializers#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#5)]

Das vorherige Codebeispiel entspricht dem folgenden Code.

[!code-vb[VbVbalrCollectionInitializers#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#6)]

Es werden ausschließlich geschachtelte Wertelisten aus der ersten Schachtelungsebene an die `Add`-Methode für den Auflistungstyp gesendet. Tiefere Schachtelungsebenen werden als Arrayliterale behandelt und die geschachtelten Wertelisten werden der `Add`-Methode einer Auflistung nicht zugeordnet.

## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|---|---|
|[Gewusst wie: Erstellen einer Add-Erweiterungsmethode für einen Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)|Zeigt, wie eine Erweiterungsmethode namens `Add` erstellt wird, die zum Auffüllen einer Auflistung mit Werten von einem Auflistungsinitialisierer verwendet werden kann.|
|[Gewusst wie: Erstellen einer Auflistung für einen Auflistungsinitialisierer](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)|Zeigt, wie die Verwendung eines Auflistungsinitialisierers ermöglicht wird, indem eine `Add`-Methode in eine Auflistungsklasse eingefügt wird, die `IEnumerable` implementiert.|

## <a name="see-also"></a>Siehe auch

- [Sammlungen](../../../../visual-basic/programming-guide/concepts/collections.md)
- [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Objektinitialisierer: Benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [New-Operator](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Automatisch implementierte Eigenschaften](../../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)
- [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md) (Gewusst wie: Initialisieren einer Arrayvariable in Visual Basic)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Gewusst wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
