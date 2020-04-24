---
title: Declare Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Declare
- vb.Lib
- vb.Any
helpviewer_keywords:
- Lib keyword [Visual Basic]
- declaring procedures [Visual Basic], Declare statement
- functions [Visual Basic], function procedures
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- procedures [Visual Basic], external
- Alias keyword [Visual Basic]
- external references [Visual Basic], Visual Basic
- DLLs, declaring procedures
- Declare statement [Visual Basic]
- declarations [Visual Basic], external
- Visual Basic code, Function procedures
- As keyword [Visual Basic], in Declare statement
- resources [Visual Basic], declaring
- Public keyword [Visual Basic], Declare statement
- platform invoke, Visual Basic external references
- Sub procedures [Visual Basic], declarations
- APIs, declaring API functions
- Visual Basic code, Sub procedures
- Function procedures [Visual Basic], declaring
ms.assetid: d3f21fb0-b804-4c99-97ed-583b23894cf1
ms.openlocfilehash: 9895709076634ce156ba9d1009f79ba7ddd2ba56
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646386"
---
# <a name="declare-statement"></a>Declare Statement

Deklariert einen Verweis auf eine Prozedur, die in einer externen Datei implementiert ist.

## <a name="syntax"></a>Syntax

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Sub ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ]
' -or-
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Overloads ] _
Declare [ charsetmodifier ] [ Function ] name Lib "libname" _
[ Alias "aliasname" ] [ ([ parameterlist ]) ] [ As returntype ]
```

## <a name="parts"></a>Bestandteile

|Begriff|Definition|
|---|---|
|`attributelist`|Optional. Siehe [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).|
|`accessmodifier`|Optional. Dabei kann es sich um eine der folgenden Methoden handeln:<br /><br /> -   [Öffentlich](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Geschützt](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Freund](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [privat](../../../visual-basic/language-reference/modifiers/private.md)<br />- [Geschützter Freund](../../language-reference/modifiers/protected-friend.md)<br />- [Privat geschützt](../../language-reference/modifiers/private-protected.md)<br /><br /> Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Optional. Siehe [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).|
|`charsetmodifier`|Optional. Gibt Zeichensatz- und Dateisuchinformationen an. Dabei kann es sich um eine der folgenden Methoden handeln:<br /><br /> -   [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) (Standard)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />-   [Auto](../../../visual-basic/language-reference/modifiers/auto.md)|
|`Sub`|Optional, aber `Sub` `Function` entweder oder muss angezeigt werden. Gibt an, dass die externe Prozedur keinen Wert zurückgibt.|
|`Function`|Optional, aber `Sub` `Function` entweder oder muss angezeigt werden. Gibt an, dass die externe Prozedur einen Wert zurückgibt.|
|`name`|Erforderlich. Name dieser externen Referenz. Weitere Informationen finden Sie unter [Deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|
|`Lib`|Erforderlich. Führt `Lib` eine Klausel ein, die die externe Datei (DLL oder Coderessource) identifiziert, die eine externe Prozedur enthält.|
|`libname`|Erforderlich. Name der Datei, die die deklarierte Prozedur enthält.|
|`Alias`|Optional. Gibt an, dass die deklarierte Prozedur nicht innerhalb `name`der Datei anhand des in angegebenen Namens identifiziert werden kann. Sie geben die `aliasname`Kennung in an.|
|`aliasname`|Erforderlich, wenn `Alias` Sie das Schlüsselwort verwenden. Zeichenfolge, die die Prozedur auf zwei Arten identifiziert:<br /><br /> Der Eintragspunktname der Prozedur in ihrer`""`Datei, innerhalb von Anführungszeichen ( )<br /><br /> - oder -<br /><br /> Ein Nummernzeichen`#`( ) gefolgt von einer ganzzahligen Zahl, die die Ordinalnummer des Einstiegspunkts der Prozedur in der Datei angibt|
|`parameterlist`|Erforderlich, wenn die Prozedur Parameter annimmt. Siehe [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).|
|`returntype`|Erforderlich, `Function` wenn `Option Strict` angegeben `On`ist und ist . Datentyp des von der Prozedur zurückgegebenen Werts.|

## <a name="remarks"></a>Bemerkungen

Manchmal müssen Sie eine in einer Datei definierte Prozedur (z. B. eine DLL oder Eine Coderessource) außerhalb des Projekts aufrufen. Wenn Sie dies tun, hat der Visual Basic-Compiler keinen Zugriff auf die Informationen, die er zum ordnungsgemäßen Aufrufen der Prozedur benötigt, z. B. wo sich die Prozedur befindet, wie sie identifiziert wird, die Aufrufsequenz und den Rückgabetyp sowie den Zeichenfolgenzeichensatz, den er verwendet. Die `Declare` Anweisung erstellt einen Verweis auf ein externes Verfahren und liefert diese erforderlichen Informationen.

Sie können `Declare` nur auf Modulebene verwenden. Dies bedeutet, dass der *Deklarationskontext* für einen externen Verweis eine Klasse, Struktur oder ein Modul sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, eine Prozedur oder ein Block sein kann. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

Externe Verweise sind standardmäßig [auf Öffentlichen](../../../visual-basic/language-reference/modifiers/public.md) Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.

## <a name="rules"></a>Regeln

- **Attribute.** Sie können Attribute auf einen externen Verweis anwenden. Jedes Attribut, das Sie anwenden, wirkt sich nur in Ihrem Projekt aus, nicht in der externen Datei.

- **Modifizierer.** Externe Prozeduren werden implizit [freigegeben.](../../../visual-basic/language-reference/modifiers/shared.md) Sie können `Shared` das Schlüsselwort nicht verwenden, wenn Sie einen externen Verweis deklarieren, und Sie können den freigegebenen Status nicht ändern.

  Eine externe Prozedur kann nicht am Überschreiben, Implementieren von Schnittstellenmembern oder Behandeln von Ereignissen teilnehmen. Dementsprechend können Sie `Overrides` `Overridable`das `NotOverridable` `MustOverride`Schlüsselwort `Handles` , , `Declare` , , `Implements`oder das Schlüsselwort in einer Anweisung nicht verwenden.

- **Externer Prozedurname.** Sie müssen diesem externen Verweis nicht denselben `name`Namen (in ) geben wie den Eintragspunktnamen der Prozedur in der externen Datei (`aliasname`). Sie können `Alias` eine Klausel verwenden, um den Eintragspunktnamen anzugeben. Dies kann nützlich sein, wenn die externe Prozedur denselben Namen wie ein reservierter Visual Basic-Modifikator oder eine Variable, Prozedur oder ein anderes Programmierelement im gleichen Bereich hat.

  > [!NOTE]
  > In den meisten DLLs wird die Groß-/Kleinschreibung beachtet.

- **Externe Prozedurnummer.** Alternativ können Sie eine `Alias` Klausel verwenden, um die Ordinalnummer des Einstiegspunkts in der Exporttabelle der externen Datei anzugeben. Dazu beginnen `aliasname` Sie mit einem Nummernschild (`#`). Dies kann nützlich sein, wenn ein Beliebiges Zeichen im namen der externen Prozedur in Visual Basic nicht zulässig ist oder wenn die externe Datei die Prozedur ohne Namen exportiert.

## <a name="data-type-rules"></a>Datentypregeln

- **Parameterdatentypen.** Wenn `Option Strict` `On`dies der Option ist, müssen `parameterlist`Sie den Datentyp der einzelnen Parameter in angeben. Dabei kann es sich um einen beliebigen Datentyp oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle erachten. Innerhalb `parameterlist`verwenden Sie `As` eine Klausel, um den Datentyp des Arguments anzugeben, das an jeden Parameter übergeben werden soll.

  > [!NOTE]
  > Wenn die externe Prozedur nicht für .NET Framework geschrieben wurde, müssen Sie darauf achten, dass die Datentypen übereinstimmen. Wenn Sie beispielsweise einen externen Verweis auf eine Visual Basic `Integer` 6.0-Prozedur mit einem Parameter (16 Bit `Short` in `Declare` Visual Basic 6.0) deklarieren, müssen Sie das entsprechende Argument wie in der Anweisung identifizieren, da dies der 16-Bit-Ganzzahltyp in Visual Basic ist. `Long` Weist auch visual Basic 6.0 eine andere `Date` Datenbreite auf und wird anders implementiert.

- **Geben Sie den Datentyp zurück.** Wenn die externe `Function` Prozedur `Option Strict` `On`a ist und ist , müssen Sie den Datentyp des Wertes angeben, der an den aufrufenden Code zurückgegeben wird. Dabei kann es sich um einen beliebigen Datentyp oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle erachten.

  > [!NOTE]
  > Der Visual Basic-Compiler überprüft nicht, ob die Datentypen mit denen der externen Prozedur kompatibel sind. Bei nichtübereinstimmender Sprache generiert die Common <xref:System.Runtime.InteropServices.MarshalDirectiveException> Language Runtime zur Laufzeit eine Ausnahme.

- **Standarddatentypen.** Wenn `Option Strict` `Off` dies der Fall ist und Sie `parameterlist`den Datentyp eines Parameters in nicht angeben, konvertiert der Visual Basic-Compiler das entsprechende Argument in den [Objektdatentyp](../../../visual-basic/language-reference/data-types/object-data-type.md). Wenn Sie nicht angeben, `returntype`nimmt der Compiler den `Object`Rückgabedatentyp als .

  > [!NOTE]
  > Da Sie es mit einer externen Prozedur zu tun haben, die möglicherweise auf einer anderen Plattform geschrieben wurde, ist es gefährlich, Annahmen über Datentypen zu treffen oder sie standardmäßig zuzulassen. Es ist viel sicherer, den Datentyp jedes Parameters und ggf. des Rückgabewerts anzugeben. Dadurch wird auch die Lesbarkeit des Codes verbessert.

## <a name="behavior"></a>Verhalten

- **Umfang.** Ein externer Verweis ist in seiner gesamten Klasse, Struktur oder Modul im Gültigkeitsbereich.

- **Lebensdauer.** Ein externer Verweis hat dieselbe Lebensdauer wie die Klasse, Struktur oder das Modul, in der er deklariert wird.

- **Aufrufen einer externen Prozedur.** Sie rufen eine externe Prozedur auf `Function` `Sub` die gleiche Weise auf, wie Sie eine oder eine Prozedur aufrufen, indem Sie sie in einem Ausdruck verwenden, wenn sie einen Wert zurückgibt, oder indem Sie sie in einer [Aufrufanweisung](../../../visual-basic/language-reference/statements/call-statement.md) angeben, wenn sie keinen Wert zurückgibt.

  Sie übergeben Argumente genau wie `parameterlist` in der `Declare` Anweisung angegeben an die externe Prozedur. Berücksichtigen Sie nicht, wie die Parameter ursprünglich in der externen Datei deklariert wurden. Wenn ein Rückgabewert vorhanden ist, verwenden Sie `returntype` ihn `Declare` genau wie in der Anweisung angegeben.

- **Zeichensätze.** Sie können `charsetmodifier` angeben, wie Visual Basic Zeichenfolgen marshallen soll, wenn die externe Prozedur aufruft. Der `Ansi` Modifikator weist Visual Basic an, alle Zeichenfolgen `Unicode` in ANSI-Werte zu marshallen, und der Modifikator weist es an, alle Zeichenfolgen zu Unicode-Werten zu marshallen. Der `Auto` Modifikator weist Visual Basic an, Zeichenfolgen gemäß .NET Framework-Regeln basierend auf dem externen Verweis `name`oder, `aliasname` falls angegeben, zu marshallen. Standardwert: `Ansi`.

  `charsetmodifier`gibt außerdem an, wie Visual Basic die externe Prozedur in seiner externen Datei nachschlagen soll. `Ansi`und `Unicode` beide leiten Visual Basic an, es nachzuschlagen, ohne seinen Namen während der Suche zu ändern. `Auto`weist Visual Basic an, den Basiszeichensatz der Laufzeitplattform zu bestimmen und möglicherweise den namen wertfür die externe Prozedur wie folgt zu ändern:

  - Auf einer ANSI-Plattform, z. B. Windows 95, Windows 98 oder Windows Millennium Edition, suchen Sie zunächst nach der externen Prozedur ohne Namensänderung. Wenn dies fehlschlägt, fügen Sie "A" an das Ende des externen Prozedurnamens an, und suchen Sie ihn erneut.

  - Auf einer Unicode-Plattform, z. B. Windows NT, Windows 2000 oder Windows XP, suchen Sie zuerst nach der externen Prozedur ohne Namensänderung. Wenn dies fehlschlägt, fügen Sie "W" an das Ende des externen Prozedurnamens an, und suchen Sie ihn erneut.

- **Mechanismus.** Visual Basic verwendet den .NET *Framework-Aufrufmechanismus* (PInvoke), um externe Prozeduren aufzulösen und darauf zuzugreifen. Die `Declare` Anweisung <xref:System.Runtime.InteropServices.DllImportAttribute> und die Klasse verwenden diesen Mechanismus automatisch, und Sie benötigen keine Kenntnisse von PInvoke. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).

> [!IMPORTANT]
> Wenn die externe Prozedur außerhalb der Common Language Runtime (CLR) ausgeführt wird, handelt es sich um *nicht verwalteten Code*. Wenn Sie eine solche Prozedur aufrufen, z. B. eine Windows-API-Funktion oder eine COM-Methode, können Sie Ihre Anwendung Sicherheitsrisiken aussetzen. Weitere Informationen finden Sie unter [Secure Coding Guidelines for Unmanaged Code](https://docs.microsoft.com/previous-versions/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein `Function` externer Verweis auf eine Prozedur deklariert, die den aktuellen Benutzernamen zurückgibt. Anschließend wird das `GetUserNameA` externe Verfahren `getUser` als Teil des Verfahrens bezeichnet.

[!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]

## <a name="example"></a>Beispiel

Der <xref:System.Runtime.InteropServices.DllImportAttribute> bietet eine alternative Möglichkeit, Funktionen in nicht verwaltetem Code zu verwenden. Im folgenden Beispiel wird eine `Declare` importierte Funktion ohne Verwendung einer Anweisung deklariert.

[!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]

[!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Imports-Anweisung (.NET-Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [AdresseDes Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Call-Anweisung](../../../visual-basic/language-reference/statements/call-statement.md)
- [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
