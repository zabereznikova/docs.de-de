---
title: Const-Anweisung
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 1411e019058e7aac8249b7a50ecd295885a74177
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354130"
---
# <a name="const-statement-visual-basic"></a>Const-Anweisung (Visual Basic)

Deklariert und definiert eine oder mehrere Konstanten.

## <a name="syntax"></a>Syntax

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ]
Const constantlist
```

## <a name="parts"></a>-Komponenten

`attributelist`  
Optional. Liste der Attribute, die für alle Konstanten gelten, die in dieser Anweisung deklariert werden. Weitere Informationen finden Sie in der [Attribut Liste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`" und "`>`").

`accessmodifier`  
Optional. Verwenden Sie diese Angabe, um anzugeben, welcher Code auf diese Konstanten zugreifen kann. Kann [öffentlich](../../../visual-basic/language-reference/modifiers/public.md), [geschützt](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [geschützter Freund](../modifiers/protected-friend.md), [Privat](../../../visual-basic/language-reference/modifiers/private.md)oder [Privat geschützt](../../language-reference/modifiers/private-protected.md)sein.

`Shadows`  
Optional. Verwenden Sie dieses Element, um ein Programmier Element in einer Basisklasse erneut zu deklarieren und auszublenden. Siehe [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).

`constantlist`  
Erforderlich Liste der Konstanten, die in dieser Anweisung deklariert werden.

`constant` `[ ,` `constant` `... ]`

Jede `constant` weist folgende Syntax und Bestandteile auf:

`constantname` `[ As` `datatype` `] =` `initializer`

|-Komponente|Beschreibung|
|----------|-----------------|
|`constantname`|Erforderlich Der Name der Konstanten. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|
|`datatype`|Erforderlich, wenn `Option Strict` `On`ist. Der Datentyp der Konstanten.|
|`initializer`|Erforderlich Ausdruck, der zur Kompilierzeit ausgewertet und der Konstante zugewiesen wird.|

## <a name="remarks"></a>Hinweise

Wenn Sie über einen Wert verfügen, der in Ihrer Anwendung nie geändert wird, können Sie eine benannte Konstante definieren und anstelle eines Literalwerts verwenden. Ein Name ist leichter zu merken als ein Wert. Sie können die Konstante nur einmal definieren und an vielen Stellen im Code verwenden. Wenn Sie in einer späteren Version den Wert neu definieren müssen, ist die `Const`-Anweisung die einzige Stelle, an der Sie eine Änderung vornehmen müssen.

Sie können `Const` nur auf Modul-oder Prozedur Ebene verwenden. Dies bedeutet, dass der *Deklarations Kontext* für eine Variable eine Klasse, eine Struktur, ein Modul, eine Prozedur oder ein Block sein muss und weder eine Quelldatei, ein Namespace noch eine Schnittstelle sein darf. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

Lokale Konstanten (innerhalb einer Prozedur) werden standardmäßig öffentlich zugänglich sein, und Sie können keine Zugriffsmodifizierer verwenden. Klassen-und Modulmember Konstanten (außerhalb einer beliebigen Prozedur) werden standardmäßig auf privaten Zugriff und Strukturmember-Konstanten standardmäßig auf den öffentlichen Zugriff eingestellt. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.

## <a name="rules"></a>Regeln

- **Deklarations Kontext.** Eine auf Modulebene deklarierte Konstante außerhalb einer Prozedur ist eine Element *Konstante*. Es ist ein Member der Klasse, Struktur oder des Moduls, das Sie deklariert.

  Eine auf Prozedur Ebene deklarierte Konstante ist eine *lokale Konstante*. Sie ist für die Prozedur oder den Block, der Sie deklariert, lokal.

- **Legt.** Attribute können nur auf Element Konstanten, nicht auf lokale Konstanten angewendet werden. Ein Attribut trägt Informationen zu den Metadaten der Assembly bei, was für temporäre Speicherung, z. b. lokale Konstanten, nicht sinnvoll ist.

- **Modifizierer.** Standardmäßig sind alle Konstanten `Shared`, `Static`und `ReadOnly`. Beim Deklarieren einer Konstanten können Sie keines dieser Schlüsselwörter verwenden.

  Auf Prozedur Ebene können Sie keine `Shadows` oder Zugriffsmodifizierer verwenden, um lokale Konstanten zu deklarieren.

- **Mehrere Konstanten.** Sie können mehrere Konstanten in derselben Deklarations Anweisung deklarieren und dabei den `constantname` Teil für jede Deklaration angeben. Mehrere Konstanten werden durch Kommas getrennt.

## <a name="data-type-rules"></a>Datentyp Regeln

- **Datentypen.** Die `Const`-Anweisung kann den Datentyp einer Variablen deklarieren. Sie können einen beliebigen Datentyp oder den Namen einer Enumeration angeben.

- **Der Standardtyp.** Wenn Sie `datatype`nicht angeben, nimmt die Konstante den Datentyp `initializer`. Wenn Sie sowohl `datatype` als auch `initializer`angeben, muss der Datentyp von `initializer` in `datatype`konvertiert werden können. Wenn weder `datatype` noch `initializer` vorhanden ist, wird der Datentyp standardmäßig `Object`.

- **Verschiedene Typen.** Sie können unterschiedliche Datentypen für unterschiedliche Konstanten angeben, indem Sie für jede deklarierte Variable eine separate `As`-Klausel verwenden. Es ist jedoch nicht möglich, mehrere Konstanten mithilfe einer Common `As`-Klausel in denselben Typ zu deklarieren.

- **Initialisierung.** Sie müssen den Wert jeder Konstanten in `constantlist`initialisieren. Mit `initializer` können Sie einen Ausdruck angeben, der der Konstante zugewiesen werden soll. Der Ausdruck kann eine beliebige Kombination von Literalen, anderen Konstanten sein, die bereits definiert sind, und Enumerationsmembern, die bereits definiert sind. Sie können arithmetische und logische Operatoren verwenden, um solche Elemente zu kombinieren.

  In `initializer`können keine Variablen oder Funktionen verwendet werden. Sie können jedoch Konvertierungs Schlüsselwörter verwenden, z. b. `CByte` und `CShort`. Sie können auch `AscW` verwenden, wenn Sie ihn mit einer Konstanten `String` oder einem `Char` Argument aufzurufen, da dieser zur Kompilierzeit ausgewertet werden kann.

## <a name="behavior"></a>Verhalten

- **Umfang.** Auf lokale Konstanten kann nur innerhalb ihrer Prozedur oder Ihres Blocks zugegriffen werden. Auf Element Konstanten kann von überall innerhalb der Klasse, Struktur oder des Moduls zugegriffen werden.

- **Abschluss.** Code außerhalb einer Klasse, Struktur oder eines Moduls muss den Namen einer Element Konstante mit dem Namen der Klasse, Struktur oder des Moduls qualifizieren. Code außerhalb einer Prozedur oder eines Blocks kann nicht auf lokale Konstanten innerhalb dieser Prozedur oder eines Blocks verweisen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die `Const`-Anweisung verwendet, um Konstanten zur Verwendung anstelle von Literalwerten zu deklarieren.

[!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]

## <a name="example"></a>Beispiel

Wenn Sie eine Konstante mit dem Datentyp `Object`definieren, gibt der Visual Basic Compiler dem Typ `initializer`anstelle der `Object`. Im folgenden Beispiel enthält die Konstante `naturalLogBase` den Lauf Zeittyp `Decimal`.

[!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]

Im vorangehenden Beispiel wird die <xref:System.Type.ToString%2A>-Methode für das <xref:System.Type> Objekt verwendet, das vom [GetType-Operator](../../../visual-basic/language-reference/operators/gettype-operator.md)zurückgegeben wird, da <xref:System.Type> nicht mit `CStr`in `String` konvertiert werden kann.

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md)
- [#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md)
- [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)
- [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)
- [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Konstanten und Enumerationen](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [Konstanten und Enumerationen](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
