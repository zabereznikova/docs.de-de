---
title: Enum-Anweisung
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
ms.openlocfilehash: 976cc68d67c69ec86918962ab2dd3406d15aed9a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404731"
---
# <a name="enum-statement-visual-basic"></a>Enum-Anweisung (Visual Basic)

Deklariert eine Enumeration und definiert die Werte ihrer Member.

## <a name="syntax"></a>Syntax

```vb
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a>Bestandteile

- `attributelist`

  Optional. Liste der Attribute, die auf diese Enumeration angewendet werden. Sie müssen die [Attribut Liste](attribute-list.md) in spitzen Klammern (" `<` " und " `>` ") einschließen.

  Das <xref:System.FlagsAttribute> -Attribut gibt an, dass der Wert einer Instanz der-Enumeration mehrere Enumerationsmember enthalten kann und dass jeder Member ein Bitfeld im Enumerationswert darstellt.

- `accessmodifier`

  Optional. Gibt an, welcher Code auf diese Enumeration zugreifen kann. Kann eines der folgenden Elemente sein:

  - [Öffentlich](../modifiers/public.md)

  - [Gebieten](../modifiers/protected.md)

  - [Kollegen](../modifiers/friend.md)

  - [Privat](../modifiers/private.md)

  - [Protected Friend](../modifiers/protected-friend.md)

  - [Privat geschützt](../modifiers/private-protected.md)

- `Shadows`

  Optional. Gibt an, dass diese Enumeration ein identisch benanntes Programmier Element oder einen Satz überladener Elemente in einer Basisklasse erneut deklariert und verbirgt. Sie können Shadowing [nur für](../modifiers/shadows.md) die Enumeration selbst angeben, nicht für Member.

- `enumerationname`

  Erforderlich. Der Name der Enumeration. Informationen zu gültigen Namen finden Sie unter [deklarierte Element Namen](../../programming-guide/language-features/declared-elements/declared-element-names.md).

- `datatype`

  Optional. Datentyp der Enumeration und aller zugehörigen Member.

- `memberlist`

  Erforderlich. Liste der Element Konstanten, die in dieser Anweisung deklariert werden. Mehrere Elemente werden in einzelnen Quell Codezeilen angezeigt.

  Jede `member` weist die folgende Syntax und Teile auf:`[<attribute list>] member name [ = initializer ]`

  |Teil|BESCHREIBUNG|
  |---|---|
  |`membername`|Erforderlich. Der Name dieses Members.|
  |`initializer`|Optional. Ausdruck, der zum Zeitpunkt der Kompilierung ausgewertet und diesem Member zugewiesen wird.|

- `End` `Enum`

  Beendet den `Enum`-Block.

## <a name="remarks"></a>Bemerkungen

Wenn Sie über eine Reihe von unveränderlichen Werten verfügen, die logisch miteinander verknüpft sind, können Sie diese in einer Enumeration definieren. Dies stellt aussagekräftige Namen für die Enumeration und ihre Member bereit, die leichter zu merken sind als ihre Werte. Sie können dann die Enumerationsmember an vielen Stellen in Ihrem Code verwenden.

Zu den Vorteilen der Verwendung von Enumerationen zählen die folgenden:

- Reduziert Fehler, die durch das übertragen oder falsch formatiping von Zahlen verursacht werden

- Erleichtert das Ändern von Werten in der Zukunft.

- Erleichtert das Lesen von Code, was bedeutet, dass es weniger wahrscheinlich ist, dass Fehler eingeführt werden.

- Gewährleistet die Vorwärtskompatibilität. Wenn Sie Enumerationen verwenden, ist es wahrscheinlich, dass Ihr Code fehlschlägt, wenn Sie in der Zukunft die Werte ändern, die den Elementnamen entsprechen.

Eine Enumeration verfügt über einen Namen, einen zugrunde liegenden Datentyp und einen Satz von Membern. Jeder Member stellt eine Konstante dar.

Eine Enumeration, die auf Klassen-, Struktur-, Modul-oder Schnittstellen Ebene, außerhalb einer Prozedur deklariert wurde, ist eine *Member-Enumeration*. Es ist ein Member der Klasse, der Struktur, des Moduls oder der Schnittstelle, die ihn deklariert.

Auf Member-Enumerationen kann von überall in ihrer Klasse, Struktur, Modul oder Schnittstelle zugegriffen werden. Code außerhalb einer Klasse, Struktur oder eines Moduls muss den Namen einer Member-Enumeration mit dem Namen der Klasse, Struktur oder des Moduls qualifizieren. Sie können verhindern, dass voll qualifizierte Namen verwendet werden, indem Sie der Quelldatei eine [Imports](imports-statement-net-namespace-and-type.md) -Anweisung hinzufügen.

Eine Enumeration, die auf Namespace Ebene, außerhalb einer Klasse, Struktur, eines Moduls oder einer Schnittstelle deklariert wurde, ist ein Member des Namespace, in dem Sie angezeigt wird.

Der *Deklarations Kontext* für eine Enumeration muss eine Quelldatei, ein Namespace, eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein, und es darf sich nicht um eine Prozedur handeln. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).

Sie können Attribute auf eine Enumeration als Ganzes anwenden, jedoch nicht auf die zugehörigen Elemente einzeln. Ein Attribut trägt Informationen zu den Metadaten der Assembly bei.

## <a name="data-type"></a>Datentyp

Die- `Enum` Anweisung kann den Datentyp einer Enumeration deklarieren. Jeder Member nimmt den Datentyp der Enumeration an. Sie können `Byte` , `Integer` , `Long` , `SByte` , `Short` , `UInteger` , oder angeben `ULong` `UShort` .

Wenn Sie `datatype` für die-Enumeration nicht angeben, wird für jedes Element der Datentyp des-Elements benötigt `initializer` . Wenn Sie sowohl `datatype` als auch angeben `initializer` , muss der Datentyp von `initializer` in konvertierbar sein `datatype` . Wenn weder `datatype` noch `initializer` vorhanden ist, lautet der Datentyp standardmäßig `Integer` .

## <a name="initializing-members"></a>Initialisieren von Membern

Die- `Enum` Anweisung kann den Inhalt ausgewählter Elemente in initialisieren `memberlist` . Verwenden Sie `initializer` , um einen Ausdruck anzugeben, der dem Member zugewiesen werden soll.

Wenn Sie `initializer` für einen Member nicht angeben, Visual Basic ihn entweder mit NULL (wenn es sich um den ersten in handelt `member` `memberlist` ) oder auf einen Wert, der größer als der unmittelbar vorangehende ist, initialisiert `member` .

Der in jeder angegebene Ausdruck `initializer` kann eine beliebige Kombination von Literalen, anderen Konstanten, die bereits definiert sind, und Enumerationsmembern sein, die bereits definiert sind, einschließlich eines vorherigen Members dieser Enumeration. Sie können arithmetische und logische Operatoren verwenden, um solche Elemente zu kombinieren.

Sie können in keine Variablen oder Funktionen verwenden `initializer` . Sie können jedoch Konvertierungs Schlüsselwörter wie `CByte` und verwenden `CShort` . Sie können auch verwenden `AscW` , wenn Sie ihn mit einer Konstante `String` oder einem Argument aufzurufen `Char` , da dieser zur Kompilierzeit ausgewertet werden kann.

Enumerationen dürfen keine Gleit Komma Werte aufweisen. Wenn einem Element ein Gleit Komma Wert zugewiesen wird und auf `Option Strict` on festgelegt ist, tritt ein Compilerfehler auf. Wenn deaktiviert `Option Strict` ist, wird der Wert automatisch in den- `Enum` Typ konvertiert.

Wenn der Wert eines Members den zulässigen Bereich des zugrunde liegenden Datentyps überschreitet oder wenn Sie ein beliebiges Element mit dem maximalen Wert initialisieren, der durch den zugrunde liegenden Datentyp zulässig ist, meldet der Compiler einen Fehler.

## <a name="modifiers"></a>Modifizierer

Klassen-, Struktur-, Modul-und Schnittstellenmember-Enumerationen werden standardmäßig auf Public Access eingestellt. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Namespace-Member-Enumerationen werden standardmäßig auf Friend-Zugriff. Sie können Ihre Zugriffsebenen an Public, aber nicht an private oder geschützte Einstellungen anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

Alle Enumerationsmember haben öffentlichen Zugriff, und Sie können keine Zugriffsmodifizierer verwenden. Wenn jedoch die Enumeration selbst über eine eingeschränktere Zugriffsebene verfügt, hat die angegebene enumerationszugriffsebene Vorrang.

Standardmäßig sind alle Enumerationen Typen, und ihre Felder sind Konstanten. Daher `Shared` können die `Static` `ReadOnly` Schlüsselwörter, und beim Deklarieren einer Enumeration oder ihrer Member nicht verwendet werden.

## <a name="assigning-multiple-values"></a>Zuweisen von mehreren Werten

Enumerationen stellen in der Regel gegenseitig ausschließende Werte dar. Indem Sie das- <xref:System.FlagsAttribute> Attribut in die- `Enum` Deklaration einschließen, können Sie einer Instanz der-Enumeration stattdessen mehrere Werte zuweisen. Das- <xref:System.FlagsAttribute> Attribut gibt an, dass die Enumeration als Bitfeld, d. h. als Satz von Flags, behandelt werden soll. Diese werden als *bitweise* Enumerationen bezeichnet.

Wenn Sie eine Enumeration mit dem-Attribut deklarieren <xref:System.FlagsAttribute> , empfiehlt es sich, für die-Werte die Kräfte 2, d. h. 1, 2, 4, 8, 16 usw., zu verwenden. Wir empfehlen auch, dass "None" der Name eines Members ist, dessen Wert 0 ist. Weitere Richtlinien finden Sie unter <xref:System.FlagsAttribute> und <xref:System.Enum> .

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie Sie die Anweisung `Enum` verwenden. Beachten Sie, dass der Member als `EggSizeEnum.Medium` und nicht als bezeichnet wird `Medium` .

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a>Beispiel

Die-Methode im folgenden Beispiel befindet sich außerhalb der- `Egg` Klasse. Daher `EggSizeEnum` ist voll qualifiziert als `Egg.EggSizeEnum` .

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die- `Enum` Anweisung verwendet, um einen verknüpften Satz benannter konstanter Werte zu definieren. In diesem Fall sind die Werte Farben, die Sie zum Entwerfen von Dateneingabe Formularen für eine Datenbank auswählen können.

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt Werte, die positive und negative Zahlen enthalten.

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine- `As` Klausel verwendet, um den einer `datatype` Enumeration anzugeben.

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie eine bitweise-Enumeration verwendet wird. Einer Instanz einer bitweisen Enumeration können mehrere Werte zugewiesen werden. Die- `Enum` Deklaration enthält das- <xref:System.FlagsAttribute> Attribut, das angibt, dass die Enumeration als ein Satz von Flags behandelt werden kann.

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a>Beispiel

Das folgende Beispiel durchläuft eine-Enumeration. Es verwendet die <xref:System.Enum.GetNames%2A> -Methode, um ein Array mit Elementnamen aus der-Enumeration abzurufen und <xref:System.Enum.GetValues%2A> ein Array von Element Werten abzurufen.

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Const-Anweisung](const-statement.md)
- [Dim-Anweisung](dim-statement.md)
- [Implizite und explizite Konvertierungen](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Konstanten und Enumerationen](../constants-and-enumerations.md)
