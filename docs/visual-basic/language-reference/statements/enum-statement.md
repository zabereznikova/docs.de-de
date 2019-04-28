---
title: Enum-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: fa97a374d4570e014222bf44844271b3394453da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638128"
---
# <a name="enum-statement-visual-basic"></a>Enum-Anweisung (Visual Basic)

Deklariert eine Enumeration und definiert die Werte ihrer Member.

## <a name="syntax"></a>Syntax

```
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a>Teile

- `attributelist`

  Dies ist optional. Liste der Attribute, die auf diese Enumeration anwenden. Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").

  Die <xref:System.FlagsAttribute> -Attribut gibt an, dass der Wert einer Instanz der Enumeration mehrere Enumerationsmember enthalten kann und jedes Element ein Bit-Feld in der Enumerationswert darstellt.

- `accessmodifier`

  Dies ist optional. Gibt an, welcher Code auf diese Enumeration zugreifen kann. Einer der folgenden Werte ist möglich:

  - [Public](../../../visual-basic/language-reference/modifiers/public.md)

  - [Protected](../../../visual-basic/language-reference/modifiers/protected.md)

  - [Friend](../../../visual-basic/language-reference/modifiers/friend.md)

  - [Private](../../../visual-basic/language-reference/modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

- `Shadows`

  Dies ist optional. Gibt an, dass diese Enumeration wird ausgeblendet, ein identisch benanntes Programmierelement oder einen Satz überladener Elemente in einer Basisklasse erneut deklariert. Sie können angeben, [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) nur auf die Enumeration selbst, nicht auf einem ihrer Member.

- `enumerationname`

  Erforderlich. Der Name der Enumeration. Weitere Informationen zu gültigen Namen finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).

- `datatype`

  Dies ist optional. Der Datentyp der Enumeration und allen zugehörigen Membern.

- `memberlist`

  Erforderlich. Liste der Memberkonstanten, die in dieser Anweisung deklariert wird. Mehrere Elemente, die auf einzelne Quellcodezeilen angezeigt werden.

  Jede `member` hat die folgende Syntax und Bestandteile: `[<attribute list>] member name [ = initializer ]`

  |Segment|Beschreibung|
  |---|---|
  |`membername`|Erforderlich. Der Name des Elements.|
  |`initializer`|Dies ist optional. Ein Ausdruck, der zur Kompilierzeit ausgewertet und auf diesen Member zugewiesen.|

- `End` `Enum`

  Beendet den `Enum`-Block.

## <a name="remarks"></a>Hinweise

Wenn Sie einen Satz von unveränderlichen Werten, die logisch miteinander verknüpft sind verfügen, können Sie diese zusammen in einer Enumeration definieren. Dadurch aussagekräftige Namen für die Enumeration und ihre Member, die leichter merken als ihre Werte sind. Sie können dann ein Member der Enumeration an vielen Stellen in Ihrem Code verwenden.

Die Vorteile der Verwendung von Enumerationen umfassen Folgendes:

- Fehler aufgrund eines Transponieren oder falsch eingegebene Zahlen wird reduziert.

- Erleichtert die Werte in der Zukunft ändern.

- Macht Code einfacher zu lesen, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler eingeführt werden.

- Stellt Aufwärtskompatibilität sicher. Bei Verwendung von Enumerationen ist der Code weniger wahrscheinlich fehlschlägt, wenn in der Zukunft jemand die Namen der entsprechenden Werte ändert.

Eine Enumeration verfügt über einen Namen, einen zugrunde liegenden Datentyp und eine Menge von Elementen. Jedes Element stellt eine Konstante dar.

Eine Enumeration, die auf die Klasse, Struktur, Modul oder Schnittstellenebene außerhalb einer Prozedur, deklariert ist eine *von Memberenumeration*. Es ist ein Mitglied der Klasse, Struktur, Modul oder Schnittstelle, die es deklariert wird.

Memberenumerationen können von überall innerhalb ihrer Klasse, Struktur, Modul oder Schnittstelle zugegriffen werden. Code außerhalb einer Klasse, einer Struktur oder eines Moduls muss ein der Memberenumeration den Namen durch den Namen dieser Klasse, Struktur oder Modul qualifizieren. Sie können vermeiden, müssen vollqualifizierte Namen verwenden, durch das Hinzufügen einer [Importe](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) Anweisung, um die Quelldatei.

Eine Enumeration, die auf Namespace-Ebene, außerhalb jeder Klasse, Struktur, Modul oder Schnittstelle, deklariert ist, ein Mitglied der Namespace, in dem er angezeigt wird.

Die *Deklarationskontext* für eine Enumeration, eine Quelldatei, Namespace, Klasse, Struktur, Modul oder Schnittstelle sein muss, und keine Prozedur sein. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

Sie können Attribute auf eine Enumeration als Ganzes, aber nicht auf ihre Member einzeln anwenden. Ein Attribut fügt Informationen an den Metadaten der Assembly.

## <a name="data-type"></a>Datentyp

Die `Enum` -Anweisung kann den Datentyp einer Enumeration deklarieren. Jedes Element hat den Enumerationstyp Daten. Sie können angeben, `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, oder `UShort`.

Wenn Sie keinen angeben `datatype` für die Enumeration nimmt jedes Element den Datentyp des seine `initializer`. Wenn Sie beide angeben `datatype` und `initializer`, der Datentyp des `initializer` müssen konvertierbar sein `datatype`. Wenn weder `datatype` noch `initializer` vorhanden ist, geben Sie die Daten standardmäßig `Integer`.

## <a name="initializing-members"></a>Initialisieren von Membern

Die `Enum` -Anweisung kann den Inhalt der ausgewählten Elemente in initialisieren `memberlist`. Verwenden Sie `initializer` , geben Sie einen Ausdruck, der das Element zugewiesen werden soll.

Wenn Sie keinen angeben `initializer` für einen Member, Visual Basic initialisiert es entweder auf 0 (null) (ist dies die erste `member` in `memberlist`), oder auf einen Wert, der um eins größer als der, der unmittelbar vorhergehende `member`.

Der Ausdruck, der in jeder bereitgestellten `initializer` kann eine beliebige Kombination aus Literalen, andere Konstanten, die bereits definiert sind und Enumerationsmember, der bereits definiert wurden, einschließlich der einen früheren Member dieser Enumeration sein. Sie können arithmetische und logische Operatoren verwenden, zur Kombination dieser Elemente.

Sie können keine Variablen oder Funktionen in `initializer`. Sie können jedoch Konvertierungsschlüsselwörter wie z. B. `CByte` und `CShort`. Sie können auch `AscW` Aufruf mit einer Konstanten `String` oder `Char` -Argument, das zum Zeitpunkt der Kompilierung ausgewertet werden können.

Enumerationen dürfen keine Gleitkommawerte haben. Wenn ein Member ein Gleitkommawerts zugewiesen ist und `Option Strict` auf festgelegt ist, tritt ein Compilerfehler auf. Wenn `Option Strict` deaktiviert ist, wird automatisch konvertierte Wert der `Enum` Typ.

Wenn der Wert eines Members des zulässigen Bereichs für den zugrunde liegenden Daten überschreitet oder Member, der zulässige Höchstwert von den zugrunde liegenden Datentyp initialisiert, meldet der Compiler einen Fehler aus.

## <a name="modifiers"></a>Modifizierer

Klasse, Struktur, Modul und Schnittstelle Member standardmäßig öffentlichen Zugriff auf Enumerationen. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Namespace Members Enumerationen standardmäßig Friend-Zugriff. Sie können ihre Zugriffsebenen auf öffentliche, aber nicht auf private oder geschützte anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

Alle Enumerationsmember verfügen über öffentlichen Zugriff und können keine Zugriffsmodifizierer auf diesen. Wenn die Enumeration selbst eine restriktivere Zugriffsebene verfügt, hat die Zugriffsebene für die angegebene Enumeration jedoch Vorrang vor.

Standardmäßig sind alle Enumerationen Typen und deren Felder sind Konstanten. Aus diesem Grund die `Shared`, `Static`, und `ReadOnly` Schlüsselwörter können nicht verwendet werden, wenn Sie eine Enumeration oder der entsprechenden Member deklarieren.

## <a name="assigning-multiple-values"></a>Zuweisen von mehreren Werten

Enumerationen stellen in der Regel sich gegenseitig ausschließende Werte dar. Durch Einschließen der <xref:System.FlagsAttribute> -Attribut in der `Enum` Deklaration, Sie können stattdessen weisen mehrere Werte mit einer Instanz der Enumeration. Die <xref:System.FlagsAttribute> Attribut gibt an, dass die Enumeration als Bitfeld, d. h. einen Satz von Flags behandelt werden. Diese heißen *bitweise* Enumerationen.

Wenn Sie eine Enumeration deklarieren, indem die <xref:System.FlagsAttribute> -Attribut, es wird empfohlen, dass Sie die Potenzen von 2, das, 1, 2, 4, 8, 16 und So weiter, für die Werte verwenden. Außerdem wird empfohlen, dass "None" der Name eines Members, dessen Wert 0 ist. Zusätzliche Richtlinien finden Sie unter <xref:System.FlagsAttribute> und <xref:System.Enum>.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie Sie die Anweisung `Enum` verwenden. Beachten Sie, die das Element als bezeichnet `EggSizeEnum.Medium`, und nicht als `Medium`.

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a>Beispiel

Die Methode im folgenden Beispiel befindet sich außerhalb der `Egg` Klasse. Aus diesem Grund `EggSizeEnum` ist als vollqualifizierte `Egg.EggSizeEnum`.

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die `Enum` Anweisung, um eine zusammengehörige Gruppe von definieren benannte Konstanten. In diesem Fall sind die Werte, Farben, die Sie auswählen können, um Dateneingabeformulare für eine Datenbank entwerfen.

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die Werte, die positive und negative Zahlen enthalten.

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel eine `As` -Klausel wird verwendet, an die `datatype` einer Enumeration.

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie eine bitweise Enumeration verwendet wird. Eine Instanz einer Enumeration bitweise können mehrere Werte zugewiesen werden. Die `Enum` Deklaration enthält die <xref:System.FlagsAttribute> -Attribut, das gibt an, dass die Enumeration als ein Satz von Flags behandelt werden kann.

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a>Beispiel

Das folgende Beispiel durchläuft eine Enumeration ab. Er verwendet die <xref:System.Enum.GetNames%2A> Methode, um ein Array von Namen aus der Enumeration abzurufen und <xref:System.Enum.GetValues%2A> um ein Array von Memberwerten abzurufen.

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)
- [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konstanten und Enumerationen](../../../visual-basic/language-reference/constants-and-enumerations.md)
