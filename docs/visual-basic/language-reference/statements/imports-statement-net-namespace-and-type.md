---
title: 'Imports-Anweisung: .NET-Namespace und-Typ'
ms.date: 07/20/2015
f1_keywords:
- vb.Imports
- imports
helpviewer_keywords:
- declared element names [Visual Basic], qualification
- imports [Visual Basic]
- Imports statement [Visual Basic]
- aliases [Visual Basic], Imports statement
- container elements [Visual Basic]
- namespaces [Visual Basic], importing
- Imports statement [Visual Basic], syntax
- import aliases [Visual Basic]
- aliases [Visual Basic], import
- declared elements [Visual Basic], container elements
ms.assetid: 7062f8aa-d890-4232-9eed-92836e13fb6e
ms.openlocfilehash: 39fa4e74f973bcb575b5751c387c0b879f4e398d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351070"
---
# <a name="imports-statement-net-namespace-and-type"></a>Imports-Anweisung (.NET-Namespace und Typ)

Ermöglicht, dass Typnamen ohne Namespace Qualifikation referenziert werden.

## <a name="syntax"></a>Syntax

```vb
Imports [ aliasname = ] namespace
' -or-
Imports [ aliasname = ] namespace.element
```

## <a name="parts"></a>-Komponenten

|Begriff|Definition|
|---|---|
|`aliasname`|Optional. Ein *importieralias* oder Name, mit dem Code auf `namespace` anstatt auf die vollständige Qualifikations Zeichenfolge verweisen kann. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`namespace`|Erforderlich Der voll qualifizierte Name des zu importierenden Namespace. Kann eine Zeichenfolge von Namespaces sein, die auf eine beliebige Ebene eingebettet ist.|
|`element`|Optional. Der Name eines Programmier Elements, das im-Namespace deklariert wird. Kann ein beliebiges Containerelement sein.|

## <a name="remarks"></a>Hinweise

Die `Imports`-Anweisung ermöglicht, dass Typen, die in einem bestimmten Namespace enthalten sind, direkt referenziert werden.

Sie können einen einzelnen Namespace Namen oder eine Zeichenfolge von schsted Namespaces angeben. Jeder untergeordnete Namespace wird von dem nächsthöheren Namespace der höheren Ebene um einen Zeitraum (`.`) getrennt, wie im folgenden Beispiel veranschaulicht:

```vb
Imports System.Collections.Generic
```

Jede Quelldatei kann eine beliebige Anzahl von `Imports`-Anweisungen enthalten. Diese müssen allen Options Deklarationen folgen, wie z. b. der `Option Strict`-Anweisung, und Sie müssen vor allen Deklarationen von Programmier Elementen stehen, wie z. b. `Module` oder `Class` Anweisungen.

Sie können `Imports` nur auf Dateiebene verwenden. Dies bedeutet, dass der Deklarations Kontext für Importe eine Quelldatei sein muss und kein Namespace, keine Klasse, keine Struktur, kein Modul, keine Schnittstelle, keine Prozedur oder kein Block sein kann.

Beachten Sie, dass die `Imports`-Anweisung keine Elemente aus anderen Projekten und Assemblys für Ihr Projekt verfügbar macht. Beim Importieren wird kein Verweis festgelegt. Es entfällt nur die Notwendigkeit, Namen zu qualifizieren, die bereits für Ihr Projekt verfügbar sind. Weitere Informationen finden Sie unter "Importieren enthaltender Elemente" in [Verweise auf deklarierte Elemente](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

> [!NOTE]
> Sie können implizite `Imports` Anweisungen definieren, indem Sie die [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)verwenden. Weitere Informationen finden Sie unter Vorgehens [Weise: Hinzufügen oder Entfernen von importierten Namespaces (Visual Basic)](/visualstudio/ide/how-to-add-or-remove-imported-namespaces-visual-basic).

## <a name="import-aliases"></a>Importaliase

Ein *importieralias* definiert den Alias für einen Namespace oder Typ. Import Aliase sind nützlich, wenn Sie Elemente mit demselben Namen verwenden müssen, die in einem oder mehreren Namespaces deklariert werden. Weitere Informationen und ein Beispiel finden Sie unter "qualifizieren eines Element namens" in [Verweise auf deklarierte Elemente](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

Sie sollten keinen Member auf Modulebene mit dem gleichen Namen wie `aliasname`deklarieren. Wenn Sie dies tun, verwendet der Visual Basic Compiler `aliasname` nur für das deklarierte Element und erkennt ihn nicht mehr als importieralias.

Obwohl die Syntax, die zum Deklarieren eines importierungsalias verwendet wird, wie zum Importieren eines XML-Namespace Präfixes verwendet wird, unterscheiden sich die Ergebnisse. Ein importieralias kann als Ausdruck in Ihrem Code verwendet werden, wohingegen ein XML-Namespace Präfix nur in XML-Literalen oder XML-Achsen Eigenschaften als Präfix für einen qualifizierten Element-oder Attributnamen verwendet werden kann.

### <a name="element-names"></a>Elementnamen

Wenn Sie `element`bereitstellen, muss es ein *Containerelement*, d. h. ein Programmier Element, das andere Elemente enthalten kann, darstellen. Container Elemente enthalten Klassen, Strukturen, Module, Schnittstellen und Enumerationen.

Der Bereich der Elemente, die von einer `Imports`-Anweisung zur Verfügung gestellt werden, hängt davon ab, ob Sie `element`angeben. Wenn Sie nur `namespace`angeben, sind alle eindeutig benannten Member dieses Namespace sowie Member von Container Elementen innerhalb dieses Namespace ohne Qualifikation verfügbar. Wenn Sie sowohl `namespace` als auch `element`angeben, sind nur die Member dieses Elements ohne Qualifizierung verfügbar.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden alle Ordner im Verzeichnis " *C:\\* " mit der <xref:System.IO.DirectoryInfo>-Klasse zurückgegeben:

Der Code enthält keine `Imports`-Anweisungen am Anfang der Datei. Daher sind die <xref:System.IO.DirectoryInfo>-, <xref:System.Text.StringBuilder>-und <xref:Microsoft.VisualBasic.ControlChars.CrLf>-Verweise vollständig mit den-Namespaces qualifiziert.

[!code-vb[VbVbalrStatements#152](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#152)]

## <a name="example"></a>Beispiel

Das folgende Beispiel enthält `Imports`-Anweisungen für die Namespaces, auf die verwiesen wird. Daher müssen die Typen nicht vollständig mit den Namespaces qualifiziert werden.

[!code-vb[VbVbalrStatements#153](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#153)]

[!code-vb[VbVbalrStatements#154](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#154)]
  
## <a name="example"></a>Beispiel

Das folgende Beispiel schließt `Imports`-Anweisungen ein, die Aliase für die Namespaces erstellen, auf die verwiesen wird. Die Typen werden mit den Aliasen qualifiziert.

[!code-vb[VbVbalrStatements#155](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#155)]

[!code-vb[VbVbalrStatements#156](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#156)]

## <a name="example"></a>Beispiel

Das folgende Beispiel schließt `Imports`-Anweisungen ein, die Aliase für die Typen erstellen, auf die verwiesen wird. Aliase werden verwendet, um die Typen anzugeben.

[!code-vb[VbVbalrStatements#157](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#157)]

[!code-vb[VbVbalrStatements#158](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class12.vb#158)]
  
## <a name="see-also"></a>Siehe auch

- [Namespace-Anweisung](namespace-statement.md)
- [Namespaces in Visual Basic](../../programming-guide/program-structure/namespaces.md)
- [Verweise und die Imports-Anweisung](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [Imports-Anweisung (XML-Namespace)](imports-statement-xml-namespace.md)
- [Verweise auf deklarierte Elemente](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
