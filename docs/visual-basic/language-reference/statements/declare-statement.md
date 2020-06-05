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
ms.openlocfilehash: 021805508a8a053ccc8fab6f1013109bece4b6f2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404770"
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
|`attributelist`|Dies ist optional. Siehe [Attribut Liste](attribute-list.md).|
|`accessmodifier`|Optional. Kann eines der folgenden Elemente sein:<br /><br /> -   [Publikums](../modifiers/public.md)<br />-   [Gebieten](../modifiers/protected.md)<br />-   [Kollegen](../modifiers/friend.md)<br />-   [Private](../modifiers/private.md)<br />- [Geschützter Freund](../modifiers/protected-friend.md)<br />- [Privat geschützt](../modifiers/private-protected.md)<br /><br /> Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Optional. Siehe [Shadows](../modifiers/shadows.md).|
|`charsetmodifier`|Optional. Gibt die Zeichensatz-und Datei Suchinformationen an. Kann eines der folgenden Elemente sein:<br /><br /> -   [ANSI](../modifiers/ansi.md) (Standard)<br />-   [Unicode-](../modifiers/unicode.md)<br />-   [Auto](../modifiers/auto.md)|
|`Sub`|Optional, aber entweder `Sub` oder `Function` muss angezeigt werden. Gibt an, dass die externe Prozedur keinen Wert zurückgibt.|
|`Function`|Optional, aber entweder `Sub` oder `Function` muss angezeigt werden. Gibt an, dass die externe Prozedur einen Wert zurückgibt.|
|`name`|Erforderlich. Der Name dieses externen Verweises. Weitere Informationen finden Sie unter [deklarierte Element Namen](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`Lib`|Erforderlich. Führt eine- `Lib` Klausel ein, die die externe Datei (dll-oder Code Ressource) identifiziert, die eine externe Prozedur enthält.|
|`libname`|Erforderlich. Der Name der Datei, die die deklarierte Prozedur enthält.|
|`Alias`|Optional. Gibt an, dass die deklarierte Prozedur nicht innerhalb der Datei durch den in angegebenen Namen identifiziert werden kann `name` . Sie geben die Identifizierung in an `aliasname` .|
|`aliasname`|Erforderlich, wenn Sie das- `Alias` Schlüsselwort verwenden. Eine Zeichenfolge, die die Prozedur auf zwei Arten identifiziert:<br /><br /> Der Einstiegspunkt Name der Prozedur innerhalb der Datei in Anführungszeichen ( `""` ).<br /><br /> Oder<br /><br /> Ein Nummern Zeichen ( `#` ) gefolgt von einer ganzen Zahl, die die Ordinalzahl des Einstiegs Punkts der Prozedur innerhalb der Datei angibt.|
|`parameterlist`|Erforderlich, wenn die Prozedur Parameter annimmt. Siehe [Parameter Liste](parameter-list.md).|
|`returntype`|Erforderlich, wenn `Function` angegeben wird und den Wert hat `Option Strict` `On` . Datentyp des Werts, der von der Prozedur zurückgegeben wird.|

## <a name="remarks"></a>Bemerkungen

Manchmal müssen Sie eine Prozedur, die in einer Datei (z. b. eine DLL-oder Code Ressource) definiert ist, außerhalb des Projekts aufruft. Wenn Sie dies tun, hat der Visual Basic Compiler keinen Zugriff auf die Informationen, die er benötigt, um die Prozedur ordnungsgemäß aufzurufen, z. b. wo sich die Prozedur befindet, wie Sie identifiziert wird, welche Aufruf Sequenz und welcher Rückgabetyp verwendet werden und welcher Zeichensatz verwendet wird. Die `Declare` -Anweisung erstellt einen Verweis auf eine externe Prozedur und stellt diese erforderlichen Informationen bereit.

Sie können `Declare` nur auf Modulebene verwenden. Dies bedeutet, dass der *Deklarations Kontext* für einen externen Verweis eine Klasse, eine Struktur oder ein Modul sein muss und weder eine Quelldatei, ein Namespace noch eine Schnittstelle, eine Prozedur oder ein Block sein kann. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).

Externe Verweise werden standardmäßig auf den [öffentlichen](../modifiers/public.md) Zugriff eingestellt. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.

## <a name="rules"></a>Regeln

- **Legt.** Sie können Attribute auf einen externen Verweis anwenden. Alle Attribute, die Sie anwenden, wirken sich nur auf das Projekt aus, nicht auf die externe Datei.

- **Modifizierer.** Externe Prozeduren werden implizit frei [gegeben](../modifiers/shared.md). `Shared`Beim Deklarieren eines externen Verweises können Sie das-Schlüsselwort nicht verwenden, und Sie können den freigegebenen Status nicht ändern.

  Eine externe Prozedur kann nicht an der Überschreibung teilnehmen, Schnittstellenmember implementieren oder Ereignisse verarbeiten. Dementsprechend können Sie das-,-,-,-,- `Overrides` `Overridable` oder- `NotOverridable` `MustOverride` `Implements` `Handles` Schlüsselwort nicht in einer- `Declare` Anweisung verwenden.

- **Name der externen Prozedur.** Sie müssen diesem externen Verweis nicht denselben Namen (in `name` ) wie den Einstiegspunkt Namen der Prozedur in der externen Datei ( `aliasname` ) zuordnen. Sie können eine- `Alias` Klausel verwenden, um den Namen des Einstiegs Punkts anzugeben. Dies kann hilfreich sein, wenn die externe Prozedur den gleichen Namen wie ein Visual Basic reservierten Modifizierer oder eine Variable, Prozedur oder ein beliebiges anderes Programmier Element im gleichen Bereich hat.

  > [!NOTE]
  > Bei Namen von Einstiegspunkten in den meisten DLLs wird die Groß-/Kleinschreibung beachtet.

- **Externe Prozedur Nummer.** Alternativ können Sie eine- `Alias` Klausel verwenden, um die Ordinalzahl des Einstiegs Punkts innerhalb der Export Tabelle der externen Datei anzugeben. Zu diesem Zweck beginnen Sie `aliasname` mit einem Nummern Zeichen ( `#` ). Dies kann hilfreich sein, wenn ein beliebiges Zeichen im Namen der externen Prozedur in Visual Basic nicht zulässig ist oder wenn die externe Datei die Prozedur ohne Namen exportiert.

## <a name="data-type-rules"></a>Datentyp Regeln

- **Parameter Datentypen.** Wenn `Option Strict` ist `On` , müssen Sie den Datentyp jedes Parameters in angeben `parameterlist` . Dies kann ein beliebiger Datentyp oder der Name einer Enumeration, Struktur, Klasse oder Schnittstelle sein. In `parameterlist` verwenden Sie eine- `As` Klausel, um den Datentyp des Arguments anzugeben, das an jeden Parameter übergeben werden soll.

  > [!NOTE]
  > Wenn die externe Prozedur nicht für das .NET Framework geschrieben wurde, müssen Sie darauf achten, dass die Datentypen übereinstimmen. Wenn Sie z. b. einen externen Verweis auf eine Visual Basic 6,0-Prozedur mit einem- `Integer` Parameter (16 Bits in Visual Basic 6,0) deklarieren, müssen Sie das entsprechende Argument wie `Short` in der- `Declare` Anweisung identifizieren, da dies der 16-Bit-ganzzahlige Typ in Visual Basic ist. Ebenso `Long` hat eine andere Daten Breite in Visual Basic 6,0 und wird unter `Date` schiedlich implementiert.

- **Der Rückgabe Datentyp.** Wenn die externe Prozedur eine ist `Function` und `Option Strict` ist `On` , müssen Sie den Datentyp des Werts angeben, der an den aufrufenden Code zurückgegeben wird. Dies kann ein beliebiger Datentyp oder der Name einer Enumeration, Struktur, Klasse oder Schnittstelle sein.

  > [!NOTE]
  > Der Visual Basic-Compiler überprüft nicht, ob die Datentypen mit denen der externen Prozedur kompatibel sind. Wenn keine Übereinstimmung vorliegt, generiert das Common Language Runtime <xref:System.Runtime.InteropServices.MarshalDirectiveException> zur Laufzeit eine-Ausnahme.

- **Standard Datentypen.** Wenn den Wert `Option Strict` `Off` hat und Sie den Datentyp eines Parameters in nicht angeben `parameterlist` , konvertiert der Visual Basic Compiler das entsprechende Argument in den [Objekt Datentyp](../data-types/object-data-type.md). Wenn Sie nicht angeben `returntype` , nimmt der Compiler ebenso den Rückgabe Datentyp an `Object` .

  > [!NOTE]
  > Da Sie mit einer externen Prozedur arbeiten, die möglicherweise auf einer anderen Plattform geschrieben wurde, ist es gefährlich, Annahmen über Datentypen zu treffen oder diese standardmäßig zuzulassen. Es ist viel sicherer, den Datentyp jedes Parameters und des Rückgabewerts anzugeben, falls vorhanden. Dies verbessert auch die Lesbarkeit des Codes.

## <a name="behavior"></a>Verhalten

- **Umfang.** Ein externer Verweis ist im Gültigkeitsbereich der Klasse, Struktur oder des Moduls.

- **Amtszeit.** Ein externer Verweis hat die gleiche Lebensdauer wie die Klasse, Struktur oder das Modul, in der es deklariert ist.

- **Aufrufen einer externen Prozedur.** Sie können eine externe Prozedur auf dieselbe Weise wie eine- `Function` oder- `Sub` Prozedur –, indem Sie Sie in einem Ausdruck verwenden, wenn Sie einen-Wert zurückgibt, oder indem Sie Sie in einer- [Anweisung](call-statement.md) angeben, wenn Sie keinen Wert zurückgibt.

  Sie übergeben Argumente an die externe Prozedur genau wie `parameterlist` in der- `Declare` Anweisung angegeben. Berücksichtigen Sie nicht, wie die Parameter ursprünglich in der externen Datei deklariert wurden. Wenn ein Rückgabewert vorhanden ist, verwenden Sie ihn genauso wie `returntype` in der-Anweisung angegeben `Declare` .

- **Zeichensätze.** Sie können angeben, `charsetmodifier` wie Visual Basic Zeichen folgen Mars Hallen soll, wenn die externe Prozedur aufgerufen wird. Der `Ansi` -Modifizierer weist Visual Basic an, alle Zeichen folgen in ANSI-Werte zu Mars Hallen, und der- `Unicode` Modifizierer leitet ihn an, um alle Zeichen folgen in Unicode Der- `Auto` Modifizierer leitet Visual Basic entsprechend den .NET Framework Regeln, die auf dem externen Verweis basieren `name` , oder, falls angegeben, an `aliasname` . Der Standardwert ist `Ansi`.

  `charsetmodifier`gibt auch an, wie Visual Basic die externe Prozedur in der externen Datei nachschlagen soll. `Ansi`und `Unicode` sowohl direkt Visual Basic, um Sie zu suchen, ohne den Namen während der Suche zu ändern. `Auto`weist Visual Basic an, den Basis Zeichensatz der Laufzeitplattform zu bestimmen und den Namen der externen Prozedur möglicherweise wie folgt zu ändern:

  - Suchen Sie auf einer ANSI-Plattform, wie z. b. Windows 95, Windows 98 oder Windows Millennium Edition, zuerst die externe Prozedur ohne Namensänderung. Wenn dies nicht möglich ist, fügen Sie am Ende des Namens der externen Prozedur "A" an, und suchen Sie es erneut.

  - Suchen Sie auf einer Unicode-Plattform wie Windows NT, Windows 2000 oder Windows XP zunächst die externe Prozedur ohne Namensänderung. Wenn dies nicht möglich ist, fügen Sie "W" an das Ende des Namens der externen Prozedur an, und suchen Sie es erneut.

- **Verfahren.** Visual Basic verwendet den .NET Framework *Platform-Aufruf* (PInvoke)-Mechanismus, um externe Prozeduren aufzulösen und darauf zuzugreifen. `Declare`Diese Methode wird von der-Anweisung und der- <xref:System.Runtime.InteropServices.DllImportAttribute> Klasse automatisch verwendet, und Sie benötigen keine Kenntnisse über PInvoke. Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Aufrufen von Windows-APIs](../../programming-guide/com-interop/walkthrough-calling-windows-apis.md).

> [!IMPORTANT]
> Wenn die externe Prozedur außerhalb der Common Language Runtime (CLR) ausgeführt wird, handelt es sich hierbei um *nicht verwalteten Code*. Wenn Sie eine solche Prozedur, z. b. eine Windows-API-Funktion oder eine com-Methode, aufgerufen haben, können Sie Ihre Anwendung für Sicherheitsrisiken verfügbar machen. Weitere Informationen finden Sie unter [sichere Codierungs Richtlinien für nicht verwalteten Code](https://docs.microsoft.com/previous-versions/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein externer Verweis auf eine `Function` Prozedur deklariert, die den aktuellen Benutzernamen zurückgibt. Anschließend wird die externe Prozedur `GetUserNameA` als Teil der Prozedur aufgerufen `getUser` .

[!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]

## <a name="example"></a>Beispiel

<xref:System.Runtime.InteropServices.DllImportAttribute>Bietet eine alternative Möglichkeit der Verwendung von Funktionen in nicht verwaltetem Code. Im folgenden Beispiel wird eine importierte Funktion deklariert, ohne eine-Anweisung zu verwenden `Declare` .

[!code-vb[VbVbalrStatements#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#16)]

[!code-vb[VbVbalrStatements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#1)]

## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.ErrObject.LastDllError%2A>
- [Imports-Anweisung (.NET-Namespace und Typ)](imports-statement-net-namespace-and-type.md)
- [AddressOf-Operator](../operators/addressof-operator.md)
- [Function-Anweisung](function-statement.md)
- [Sub-Anweisung](sub-statement.md)
- [Parameterliste](parameter-list.md)
- [Call-Anweisung](call-statement.md)
- [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../programming-guide/com-interop/walkthrough-calling-windows-apis.md)
