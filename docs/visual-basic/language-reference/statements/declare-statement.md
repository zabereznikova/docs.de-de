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
ms.openlocfilehash: 48a36e3ecdef40810ea7a3194e85b5b646154331
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354093"
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

## <a name="parts"></a>-Komponenten

|Begriff|Definition|
|---|---|
|`attributelist`|Optional. Siehe [Attribut Liste](../../../visual-basic/language-reference/statements/attribute-list.md).|
|`accessmodifier`|Optional. Einer der folgenden Werte ist möglich:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [geschützt](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privat](../../../visual-basic/language-reference/modifiers/private.md)<br />- [geschützter Freund](../../language-reference/modifiers/protected-friend.md)<br />- [Privat geschützt](../../language-reference/modifiers/private-protected.md)<br /><br /> Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Optional. Siehe [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|
|`charsetmodifier`|Optional. Gibt die Zeichensatz-und Datei Suchinformationen an. Einer der folgenden Werte ist möglich:<br /><br /> -   [ANSI](../../../visual-basic/language-reference/modifiers/ansi.md) (Standard)<br />-   [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)<br />[automatisch](../../../visual-basic/language-reference/modifiers/auto.md) -   |
|`Sub`|Optional, aber entweder `Sub` oder `Function` muss angezeigt werden. Gibt an, dass die externe Prozedur keinen Wert zurückgibt.|
|`Function`|Optional, aber entweder `Sub` oder `Function` muss angezeigt werden. Gibt an, dass die externe Prozedur einen Wert zurückgibt.|
|`name`|Erforderlich Der Name dieses externen Verweises. Weitere Informationen finden Sie unter [deklarierte Element Namen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|
|`Lib`|Erforderlich Führt eine `Lib`-Klausel ein, die die externe Datei (dll-oder Code Ressource) identifiziert, die eine externe Prozedur enthält.|
|`libname`|Erforderlich Der Name der Datei, die die deklarierte Prozedur enthält.|
|`Alias`|Optional. Gibt an, dass die deklarierte Prozedur nicht innerhalb der Datei durch den in `name`angegebenen Namen identifiziert werden kann. Sie geben die Identifizierung in `aliasname`an.|
|`aliasname`|Erforderlich, wenn Sie das `Alias`-Schlüsselwort verwenden. Eine Zeichenfolge, die die Prozedur auf zwei Arten identifiziert:<br /><br /> Der Name des Einstiegs Punkts der Prozedur innerhalb der Datei in Anführungszeichen (`""`)<br /><br /> \- oder -<br /><br /> Ein Nummern Zeichen (`#`), gefolgt von einer ganzen Zahl, die die Ordinalzahl des Einstiegs Punkts der Prozedur innerhalb der Datei angibt.|
|`parameterlist`|Erforderlich, wenn die Prozedur Parameter annimmt. Siehe [Parameter Liste](../../../visual-basic/language-reference/statements/parameter-list.md).|
|`returntype`|Erforderlich, wenn `Function` angegeben und `Option Strict` `On`ist. Datentyp des Werts, der von der Prozedur zurückgegeben wird.|

## <a name="remarks"></a>Hinweise

Manchmal müssen Sie eine Prozedur, die in einer Datei (z. b. eine DLL-oder Code Ressource) definiert ist, außerhalb des Projekts aufruft. Wenn Sie dies tun, hat der Visual Basic Compiler keinen Zugriff auf die Informationen, die er benötigt, um die Prozedur ordnungsgemäß aufzurufen, z. b. wo sich die Prozedur befindet, wie Sie identifiziert wird, welche Aufruf Sequenz und welcher Rückgabetyp verwendet werden und welcher Zeichensatz verwendet wird. Die `Declare`-Anweisung erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.

Sie können `Declare` nur auf Modulebene verwenden. Dies bedeutet, dass der *Deklarations Kontext* für einen externen Verweis eine Klasse, eine Struktur oder ein Modul sein muss und weder eine Quelldatei, ein Namespace noch eine Schnittstelle, eine Prozedur oder ein Block sein kann. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

Externe Verweise werden standardmäßig auf den [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md) Zugriff eingestellt. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.

## <a name="rules"></a>Regeln

- **Legt.** Sie können Attribute auf einen externen Verweis anwenden. Alle Attribute, die Sie anwenden, wirken sich nur auf das Projekt aus, nicht auf die externe Datei.

- **Modifizierer.** Externe Prozeduren werden implizit frei [gegeben](../../../visual-basic/language-reference/modifiers/shared.md). Beim Deklarieren eines externen Verweises können Sie das `Shared`-Schlüsselwort nicht verwenden, und Sie können den freigegebenen Status nicht ändern.

  Eine externe Prozedur kann nicht an der Überschreibung teilnehmen, Schnittstellenmember implementieren oder Ereignisse verarbeiten. Dementsprechend können Sie das-Schlüsselwort `Overrides`, `Overridable`, `NotOverridable`, `MustOverride`, `Implements`oder `Handles` nicht in einer `Declare`-Anweisung verwenden.

- **Name der externen Prozedur.** Sie müssen diesen externen Verweis nicht denselben Namen (in `name`) wie den Einstiegspunkt Namen der Prozedur in der externen Datei (`aliasname`) einräumen. Sie können eine `Alias`-Klausel verwenden, um den Namen des Einstiegs Punkts anzugeben. Dies kann hilfreich sein, wenn die externe Prozedur den gleichen Namen wie ein Visual Basic reservierten Modifizierer oder eine Variable, Prozedur oder ein beliebiges anderes Programmier Element im gleichen Bereich hat.

  > [!NOTE]
  > Bei Namen von Einstiegspunkten in den meisten DLLs wird die Groß-/Kleinschreibung beachtet.

- **Externe Prozedur Nummer.** Alternativ können Sie eine `Alias`-Klausel verwenden, um die Ordinalzahl des Einstiegs Punkts innerhalb der Export Tabelle der externen Datei anzugeben. Zu diesem Zweck beginnen Sie `aliasname` mit einem Nummern Zeichen (`#`). Dies kann hilfreich sein, wenn ein beliebiges Zeichen im Namen der externen Prozedur in Visual Basic nicht zulässig ist oder wenn die externe Datei die Prozedur ohne Namen exportiert.

## <a name="data-type-rules"></a>Datentyp Regeln

- **Parameter Datentypen.** Wenn `Option Strict` `On`ist, müssen Sie den Datentyp jedes Parameters in `parameterlist`angeben. Dies kann ein beliebiger Datentyp oder der Name einer Enumeration, Struktur, Klasse oder Schnittstelle sein. In `parameterlist`verwenden Sie eine `As`-Klausel, um den Datentyp des Arguments anzugeben, das an jeden Parameter übergeben werden soll.

  > [!NOTE]
  > Wenn die externe Prozedur nicht für das .NET Framework geschrieben wurde, müssen Sie darauf achten, dass die Datentypen übereinstimmen. Wenn Sie z. b. einen externen Verweis auf eine Visual Basic 6,0-Prozedur mit einem `Integer`-Parameter (16 Bits in Visual Basic 6,0) deklarieren, müssen Sie das entsprechende Argument in der `Declare`-Anweisung als `Short` identifizieren, da dies der 16-Bit-ganzzahlige Typ in Visual Basic ist. Ebenso hat `Long` in Visual Basic 6,0 eine andere Daten Breite und `Date` unterschiedlich implementiert.

- **Der Rückgabe Datentyp.** Wenn die externe Prozedur eine `Function` ist und `Option Strict` `On`ist, müssen Sie den Datentyp des Werts angeben, der an den aufrufenden Code zurückgegeben wird. Dies kann ein beliebiger Datentyp oder der Name einer Enumeration, Struktur, Klasse oder Schnittstelle sein.

  > [!NOTE]
  > Der Visual Basic-Compiler überprüft nicht, ob die Datentypen mit denen der externen Prozedur kompatibel sind. Wenn keine Übereinstimmung vorliegt, generiert das Common Language Runtime zur Laufzeit eine <xref:System.Runtime.InteropServices.MarshalDirectiveException> Ausnahme.

- **Standard Datentypen.** Wenn `Option Strict` `Off` ist und Sie den Datentyp eines Parameters in `parameterlist`nicht angeben, konvertiert der Visual Basic Compiler das entsprechende Argument in den [Objekt Datentyp](../../../visual-basic/language-reference/data-types/object-data-type.md). Wenn Sie `returntype`nicht angeben, übernimmt der Compiler den Rückgabe Datentyp, um `Object`zu werden.

  > [!NOTE]
  > Da Sie mit einer externen Prozedur arbeiten, die möglicherweise auf einer anderen Plattform geschrieben wurde, ist es gefährlich, Annahmen über Datentypen zu treffen oder diese standardmäßig zuzulassen. Es ist viel sicherer, den Datentyp jedes Parameters und des Rückgabewerts anzugeben, falls vorhanden. Dies verbessert auch die Lesbarkeit des Codes.

## <a name="behavior"></a>Verhalten

- **Umfang.** Ein externer Verweis ist im Gültigkeitsbereich der Klasse, Struktur oder des Moduls.

- **Amtszeit.** Ein externer Verweis hat die gleiche Lebensdauer wie die Klasse, Struktur oder das Modul, in der es deklariert ist.

- **Aufrufen einer externen Prozedur.** Sie können eine externe Prozedur auf dieselbe Weise wie eine `Function` oder `Sub` Prozedur aufzurufen – indem Sie Sie in einem Ausdruck verwenden, wenn Sie einen Wert zurückgibt, oder indem Sie Sie in einer- [Anweisung](../../../visual-basic/language-reference/statements/call-statement.md) angeben, wenn Sie keinen Wert zurückgibt.

  Sie übergeben Argumente an die externe Prozedur genau so, wie Sie durch `parameterlist` in der `Declare`-Anweisung angegeben werden. Berücksichtigen Sie nicht, wie die Parameter ursprünglich in der externen Datei deklariert wurden. Wenn ein Rückgabewert vorhanden ist, verwenden Sie ihn genauso wie in `returntype` in der `Declare`-Anweisung angegeben.

- **Zeichensätze.** Sie können in `charsetmodifier` festlegen, wie Visual Basic Zeichen folgen Mars Hallen soll, wenn die externe Prozedur aufgerufen wird. Der `Ansi`-Modifizierer leitet Visual Basic, alle Zeichen folgen in ANSI-Werte zu Mars Hallen, und der `Unicode`-Modifizierer leitet ihn um, um alle Zeichen folgen in Unicode-Werte Der `Auto`-Modifizierer leitet Visual Basic Zeichen folgen gemäß den .NET Framework Regeln basierend auf dem externen Verweis `name`oder `aliasname`, falls angegeben, in den marshallt. Der Standardwert ist `Ansi`.

  `charsetmodifier` gibt auch an, wie Visual Basic die externe Prozedur innerhalb der externen Datei suchen soll. `Ansi` und `Unicode` direkt Visual Basic, um Sie zu suchen, ohne den Namen während der Suche zu ändern. `Auto` leitet Visual Basic den Basis Zeichensatz der Laufzeitplattform ab und kann ggf. den Namen der externen Prozedur wie folgt ändern:

  - Suchen Sie auf einer ANSI-Plattform, wie z. b. Windows 95, Windows 98 oder Windows Millennium Edition, zuerst die externe Prozedur ohne Namensänderung. Wenn dies nicht möglich ist, fügen Sie am Ende des Namens der externen Prozedur "A" an, und suchen Sie es erneut.

  - Suchen Sie auf einer Unicode-Plattform wie Windows NT, Windows 2000 oder Windows XP zunächst die externe Prozedur ohne Namensänderung. Wenn dies nicht möglich ist, fügen Sie "W" an das Ende des Namens der externen Prozedur an, und suchen Sie es erneut.

- **Verfahren.** Visual Basic verwendet den .NET Framework *Platform-Aufruf* (PInvoke)-Mechanismus, um externe Prozeduren aufzulösen und darauf zuzugreifen. Die `Declare`-Anweisung und die <xref:System.Runtime.InteropServices.DllImportAttribute>-Klasse verwenden diesen Mechanismus automatisch, sodass Sie keine Kenntnisse über PInvoke benötigen. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md).

> [!IMPORTANT]
> Wenn die externe Prozedur außerhalb der Common Language Runtime (CLR) ausgeführt wird, handelt es sich hierbei um *nicht verwalteten Code*. Wenn Sie eine solche Prozedur, z. b. eine Windows-API-Funktion oder eine com-Methode, aufgerufen haben, können Sie Ihre Anwendung für Sicherheitsrisiken verfügbar machen. Weitere Informationen finden Sie unter [sichere Codierungs Richtlinien für nicht verwalteten Code](../../../framework/security/secure-coding-guidelines-for-unmanaged-code.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein externer Verweis auf eine `Function` Prozedur deklariert, die den aktuellen Benutzernamen zurückgibt. Anschließend wird die externe Prozedur `GetUserNameA` als Teil der `getUser` Prozedur aufgerufen.

[!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]

## <a name="example"></a>Beispiel

Der <xref:System.Runtime.InteropServices.DllImportAttribute> bietet eine alternative Möglichkeit der Verwendung von Funktionen in nicht verwaltetem Code. Im folgenden Beispiel wird eine importierte Funktion ohne Verwendung einer `Declare`-Anweisung deklariert.

[!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]

[!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Call-Anweisung](../../../visual-basic/language-reference/statements/call-statement.md)
- [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
