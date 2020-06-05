---
title: Const-Anweisung
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 3b05d4067ef99e03df07d2c316c982051180d961
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84382106"
---
# <a name="const-statement-visual-basic"></a>Const-Anweisung (Visual Basic)

Deklariert und definiert eine oder mehrere Konstanten.

## <a name="syntax"></a>Syntax

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ]
Const constantlist
```

## <a name="parts"></a>Bestandteile

`attributelist`  
Optional. Liste der Attribute, die für alle Konstanten gelten, die in dieser Anweisung deklariert werden. Siehe [Attribut Liste](attribute-list.md) in spitzen Klammern (" `<` " und " `>` ").

`accessmodifier`  
Optional. Verwenden Sie diese Angabe, um anzugeben, welcher Code auf diese Konstanten zugreifen kann. Kann [öffentlich](../modifiers/public.md), [geschützt](../modifiers/protected.md), [Friend](../modifiers/friend.md), [geschützter Freund](../modifiers/protected-friend.md), [Privat](../modifiers/private.md)oder [Privat geschützt](../modifiers/private-protected.md)sein.

`Shadows`  
Optional. Verwenden Sie dieses Element, um ein Programmier Element in einer Basisklasse erneut zu deklarieren und auszublenden. Siehe [Shadows](../modifiers/shadows.md).

`constantlist`  
Erforderlich. Liste der Konstanten, die in dieser Anweisung deklariert werden.

`constant` `[ ,` `constant` `... ]`

Jede `constant` weist folgende Syntax und Bestandteile auf:

`constantname` `[ As` `datatype` `] =` `initializer`

|Teil|BESCHREIBUNG|
|----------|-----------------|
|`constantname`|Erforderlich. Der Name der Konstanten. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`datatype`|Erforderlich, wenn `Option Strict` ist `On` . Der Datentyp der Konstanten.|
|`initializer`|Erforderlich. Ausdruck, der zur Kompilierzeit ausgewertet und der Konstante zugewiesen wird.|

## <a name="remarks"></a>Bemerkungen

Wenn Sie über einen Wert verfügen, der in Ihrer Anwendung nie geändert wird, können Sie eine benannte Konstante definieren und anstelle eines Literalwerts verwenden. Ein Name ist leichter zu merken als ein Wert. Sie können die Konstante nur einmal definieren und an vielen Stellen im Code verwenden. Wenn Sie in einer späteren Version den Wert neu definieren müssen, ist die- `Const` Anweisung die einzige Stelle, an der Sie eine Änderung vornehmen müssen.

Sie können `Const` nur auf Modul-oder Prozedur Ebene verwenden. Dies bedeutet, dass der *Deklarations Kontext* für eine Variable eine Klasse, eine Struktur, ein Modul, eine Prozedur oder ein Block sein muss und weder eine Quelldatei, ein Namespace noch eine Schnittstelle sein darf. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).

Lokale Konstanten (innerhalb einer Prozedur) werden standardmäßig öffentlich zugänglich sein, und Sie können keine Zugriffsmodifizierer verwenden. Klassen-und Modulmember Konstanten (außerhalb einer beliebigen Prozedur) werden standardmäßig auf privaten Zugriff und Strukturmember-Konstanten standardmäßig auf den öffentlichen Zugriff eingestellt. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.

## <a name="rules"></a>Regeln

- **Deklarationskontext.** Eine auf Modulebene deklarierte Konstante außerhalb einer Prozedur ist eine Element *Konstante*. Es ist ein Member der Klasse, Struktur oder des Moduls, das Sie deklariert.

  Eine auf Prozedur Ebene deklarierte Konstante ist eine *lokale Konstante*. Sie ist für die Prozedur oder den Block, der Sie deklariert, lokal.

- **Legt.** Attribute können nur auf Element Konstanten, nicht auf lokale Konstanten angewendet werden. Ein Attribut trägt Informationen zu den Metadaten der Assembly bei, was für temporäre Speicherung, z. b. lokale Konstanten, nicht sinnvoll ist.

- **Modifizierer.** Standardmäßig sind alle Konstanten `Shared` , `Static` und `ReadOnly` . Beim Deklarieren einer Konstanten können Sie keines dieser Schlüsselwörter verwenden.

  Auf Prozedur Ebene können Sie `Shadows` oder keine Zugriffsmodifizierer verwenden, um lokale Konstanten zu deklarieren.

- **Mehrere Konstanten.** Sie können mehrere Konstanten in derselben Deklarations Anweisung deklarieren, wobei Sie `constantname` jeweils den Teil angeben. Mehrere Konstanten werden durch Kommas getrennt.

## <a name="data-type-rules"></a>Datentyp Regeln

- **Datentypen.** Die- `Const` Anweisung kann den Datentyp einer Variablen deklarieren. Sie können einen beliebigen Datentyp oder den Namen einer Enumeration angeben.

- **Der Standardtyp.** Wenn Sie nicht angeben `datatype` , nimmt die Konstante den Datentyp von an `initializer` . Wenn Sie sowohl `datatype` als auch angeben `initializer` , muss der Datentyp von `initializer` in konvertierbar sein `datatype` . Wenn weder `datatype` noch `initializer` vorhanden ist, lautet der Datentyp standardmäßig `Object` .

- **Verschiedene Typen.** Sie können unterschiedliche Datentypen für unterschiedliche Konstanten angeben, indem Sie `As` für jede deklarierte Variable eine separate Klausel verwenden. Es ist jedoch nicht möglich, mehrere Konstanten mithilfe einer Common-Klausel für denselben Typ zu deklarieren `As` .

- **Initialisierung.** Sie müssen den Wert jeder Konstanten in initialisieren `constantlist` . Verwenden Sie `initializer` , um einen Ausdruck bereitzustellen, der der Konstante zugewiesen werden soll. Der Ausdruck kann eine beliebige Kombination von Literalen, anderen Konstanten sein, die bereits definiert sind, und Enumerationsmembern, die bereits definiert sind. Sie können arithmetische und logische Operatoren verwenden, um solche Elemente zu kombinieren.

  Sie können in keine Variablen oder Funktionen verwenden `initializer` . Sie können jedoch Konvertierungs Schlüsselwörter wie `CByte` und verwenden `CShort` . Sie können auch verwenden `AscW` , wenn Sie ihn mit einer Konstante `String` oder einem Argument aufzurufen `Char` , da dieser zur Kompilierzeit ausgewertet werden kann.

## <a name="behavior"></a>Verhalten

- **Umfang.** Auf lokale Konstanten kann nur innerhalb ihrer Prozedur oder Ihres Blocks zugegriffen werden. Auf Element Konstanten kann von überall innerhalb der Klasse, Struktur oder des Moduls zugegriffen werden.

- **Abschluss.** Code außerhalb einer Klasse, Struktur oder eines Moduls muss den Namen einer Element Konstante mit dem Namen der Klasse, Struktur oder des Moduls qualifizieren. Code außerhalb einer Prozedur oder eines Blocks kann nicht auf lokale Konstanten innerhalb dieser Prozedur oder eines Blocks verweisen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die- `Const` Anweisung verwendet, um Konstanten zur Verwendung anstelle von Literalwerten zu deklarieren.

[!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]

## <a name="example"></a>Beispiel

Wenn Sie eine Konstante mit dem-Datentyp definieren `Object` , gibt der Visual Basic Compiler den Typ `initializer` anstelle von an `Object` . Im folgenden Beispiel verfügt die Konstante `naturalLogBase` über den Lauf Zeittyp `Decimal` .

[!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]

Im vorangehenden Beispiel wird die- <xref:System.Type.ToString%2A> Methode für das- <xref:System.Type> Objekt verwendet, das vom [GetType-Operator](../operators/gettype-operator.md)zurückgegeben wird, da <xref:System.Type> nicht mithilfe von konvertiert werden kann `String` `CStr` .

## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Enum-Anweisung](enum-statement.md)
- [#Const-Anweisung](../directives/const-directive.md)
- [Dim-Anweisung](dim-statement.md)
- [ReDim-Anweisung](redim-statement.md)
- [Implizite und explizite Konvertierungen](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Konstanten und Enumerationen](../../programming-guide/language-features/constants-enums/index.md)
- [Konstanten und Enumerationen](../constants-and-enumerations.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
