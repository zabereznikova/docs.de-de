---
title: Bewährte Methoden zum Schreiben von Komponententests
description: Erfahren Sie mehr über bewährte Methoden zum Schreiben von Komponententests, die die Qualität und Stabilität von Code für .NET Core- und .NET Standard-Projekte gewährleisten.
author: jpreese
ms.author: wiwagn
ms.date: 07/28/2018
ms.openlocfilehash: 6c1e9a665ad541bf6109634a6df857880ee47042
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93281648"
---
# <a name="unit-testing-best-practices-with-net-core-and-net-standard"></a>Bewährte Methoden für Komponententests mit .NET Core und .NET Standard

Komponententests bringen zahlreiche Vorteile mit sich: Sie helfen bei der Regression, stellen Dokumentation bereit und unterstützen Sie beim Entwerfen guten Codes. Allerdings können Komponententest, die schwierig zu lesen und fehleranfällig sind, zu einer unübersichtlichen Codebasis führen. In diesem Artikel werden einige bewährte Methoden in Bezug auf den Entwurf von Komponententests für Ihre .NET Core- und .NET Standard-Projekte beschrieben.

In diesem Leitfaden lernen Sie die bewährten Methoden beim Schreiben von Komponententests kennen, mit denen Sie Ihre Tests resilient und leicht verständlich gestalten können.

Von [John Reese](https://reese.dev) mit besonderem Dank an [Roy Osherove](https://osherove.com/)

## <a name="why-unit-test"></a>Weshalb sollte ich Komponententests durchführen?

### <a name="less-time-performing-functional-tests"></a>Weniger Zeitaufwand für das Ausführen von Funktionstests

Funktionstests sind kostspielig. Für Funktionstests muss normalerweise die Anwendung geöffnet werden, und Sie (oder eine andere Person) müssen mehrere Schritte ausführen, um das erwartete Verhalten zu überprüfen. Es kann durchaus sein, dass der Tester diese Schritte nicht kennt, was bedeutet, dass sich dieser an eine Person wenden muss, die sich in dem Bereich auskennt, um den Test auszuführen. Der Testvorgang selbst kann nur ein paar Sekunden für banale Änderungen oder Minuten für größere Änderungen in Anspruch nehmen. Abschließend muss der ganze Vorgang für jede Änderung, die Sie am System vornehmen, wiederholt werden.

Im Vergleich dazu benötigen Komponententests nur Millisekunden. Außerdem können sie durch einen Klick auf eine Schaltfläche ausgeführt werden und erfordern keine tiefgreifenden Kenntnisse zum System. Ob der Test erfolgreich ist oder fehlschlägt, hängt vom Testlauf und nicht von der einzelnen Person ab, die den Test ausführt.

### <a name="protection-against-regression"></a>Schutz vor Regression

Regressionsfehler sind Fehler, die auftreten, wenn eine Änderung an der Anwendung vorgenommen wird. Tester testen meist nicht nur ihr neues Feature sondern auch die Features, die zuvor schon vorhanden waren. So können sie überprüfen, ob die zuvor implementierten Features noch immer wie erwartet funktionieren.

Durch Komponententests ist es möglich, die gesamte Testsammlung nach jedem Build oder sogar nach jeder Änderung an einer Codezeile erneut durchzuführen. So können Sie sicherstellen, dass Ihr neuer Code die vorhandene Funktionalität nicht beeinträchtigt.

### <a name="executable-documentation"></a>Dokumentation zur Ausführbarkeit

Es ist nicht immer offensichtlich, was genau eine bestimmte Methode tut oder wie sie sich bei einer bestimmten Eingabe verhält. Sie fragen sich vielleicht: Wie verhält sich diese Methode, wenn ich ihr eine leere Zeichenfolge übergebe? Oder was geschieht, wenn ich NULL übergebe?

Wenn Sie über eine Sammlung von sinnvoll benannten Komponententests verfügen, sollte jeder Test die erwartete Ausgabe für eine gegebene Eingabe eindeutig erklären können. Zusätzlich sollte er überprüfen, ob sie tatsächlich funktioniert.

### <a name="less-coupled-code"></a>Weniger gekoppelter Code

Wenn Code eng gekoppelt ist, kann es schwierig sein, Komponententests dafür auszuführen. Ohne das Erstellen von Komponententests für den von Ihnen geschriebenen Code kann die Kopplung weniger offensichtlich sein.

Wenn Sie Tests für Ihren Code schreiben, wird dieser automatisch entkoppelt, da es ansonsten schwieriger wäre, diesen zu testen.

## <a name="characteristics-of-a-good-unit-test"></a>Merkmale eines guten Komponententests

- **Schnelligkeit**. Es ist nicht ungewöhnlich, dass ausgereifte Projekte Tausende von Komponententests enthalten. Die Ausführung von Komponententests sollte sehr wenig Zeit in Anspruch nehmen. Sie sollten innerhalb von Millisekunden abgeschlossen sein.
- **Unabhängigkeit**. Komponententest sind eigenständig, sie können isoliert ausgeführt werden und verfügen über keine Abhängigkeiten auf externen Faktoren, wie etwa einem Dateisystem oder einer Datenbank.
- **Wiederholbarkeit**. Das Ausführen eines Komponententests sollte immer zu den gleichen Ergebnissen führen. Wenn Sie zwischen den Ausführungen nichts ändern, sollte sich das Ergebnis auch nicht ändern.
- **Selbstprüfung**. Der Test sollte in der Lage sein, automatisch und ohne menschliches Eingreifen zu erkennen, ob er erfolgreich war oder fehlgeschlagen ist.
- **Verhältnismäßigkeit**. Ein Komponententest darf verglichen mit dem zu testenden Code nicht unverhältnismäßig lang für das Schreiben benötigen. Wenn Sie bemerken, dass der Codetest im Vergleich zum Schreiben des Codes viel Zeit in Anspruch nimmt, erwägen Sie einen Entwurf, der besser getestet werden kann.

## <a name="code-coverage"></a>Codeabdeckung

Ein hoher Code-Coverage-Prozentsatz steht oft im Zusammenhang mit einer höheren Codequalität. Durch die Messung an sich kann die Codequalität jedoch *nicht* bestimmt werden. Das Festlegen eines übermäßig ambitionierten Code-Coverage-Prozentsatzes kann kontraproduktiv sein. Stellen Sie sich ein komplexes Projekt mit Tausenden von bedingten Branches vor, und stellen Sie sich vor, dass Sie ein Code-Coverage-Ziel von 95 % festlegen. Derzeit weist das Projekt 90 % Code Coverage auf. Für die restlichen 5 % könnte für alle Grenzfälle sehr viel Zeit einkalkuliert werden müssen, und der Wertbeitrag verringert sich schnell.

Ein hoher Code-Coverage-Prozentsatz ist weder ein Erfolgsindikator noch ein Hinweis auf eine hohe Codequalität. Er stellt lediglich die Menge an Code dar, die durch Komponententests abgedeckt wird. Weitere Informationen finden Sie unter [Verwenden von Code Coverage für Komponententests](unit-testing-code-coverage.md).

## <a name="lets-speak-the-same-language"></a>Begriffsklärung

Der Begriff *Mock* (Deutsch: „Pseudo“) wird leider im Testkontext häufig falsch verwendet. Im Folgenden werden die häufigsten Arten von unechten Objekten, sogenannten *Fakes* , beim Schreiben von Komponententests definiert:

*Fake* : Fake ist ein generischer Begriff, der sowohl für Stubs als auch für Pseudoobjekte („Mocks“) verwendet wird. Ob es sich um einen Stub oder um einen Mock handelt, hängt vom Kontext ab. Das bedeutet, dass ein Fake entweder ein Stub oder ein Mock sein kann.

*Mock* : Ein Pseudoobjekt ist ein unechtes Objekt im System, das entscheidet, ob ein Komponententest erfolgreich war oder nicht. Ein Mock ist zunächst ein Fake, bis eine Assert-Anweisung ausgeführt wird.

*Stub* : Ein Stub ist ein anpassbarer Platzhalter für eine vorhandene Abhängigkeit (oder einen Projektmitarbeiter) im System. Wenn Sie einen Stub verwenden, können Sie Ihren Code testen, ohne sich direkt um die Abhängigkeit kümmern zu müssen. Standardmäßig ist ein Fake immer zunächst ein Stub.

Betrachten Sie den folgenden Codeausschnitt:

```csharp
var mockOrder = new MockOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

Dies wäre ein Beispiel eines Stubs, der als Mock bezeichnet wird. In diesem Fall handelt es sich aber um einen Stub. Sie übergeben „Order“ nur, um `Purchase` instanziieren zu können (das System, das getestet wird). Die Bezeichnung `MockOrder` ist ebenfalls irreführend, da auch hier die Reihenfolge keinen Mock darstellt.

Dies ist ein besserer Ansatz:

```csharp
var stubOrder = new FakeOrder();
var purchase = new Purchase(stubOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

Indem die Klasse in `FakeOrder` umbenannt wird, wird sie generischer und kann so als Mock oder Stub verwendet werden, je nachdem, was für die Testsituation besser geeignet ist. Im Beispiel oben wird `FakeOrder` als Stub verwendet. Sie verwenden `FakeOrder` nicht in der Assert-Anweisung. Die `FakeOrder` wurde nur an die Klasse `Purchase` übergeben, um die Anforderungen des Konstruktors zu erfüllen.

Um „Purchase“ als Mock verwenden zu können, können Sie z.B. wie folgt vorgehen:

```csharp
var mockOrder = new FakeOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(mockOrder.Validated);
```

In diesem Fall überprüfen Sie eine Eigenschaft des Fakes (d.h. führen eine Assert-Anweisung dafür aus). Im Codeausschnitt oben ist `mockOrder` also ein Mock.

> [!IMPORTANT]
> Es ist wichtig, dass die Terminologie richtig ist. Wenn Sie Ihre Stubs als „Mocks“ bezeichnen, können andere Entwickler Ihre Absicht falsch verstehen.

Der Hauptunterschied zwischen Mocks und Stubs ist also der folgende: Mocks unterscheiden sich im Grunde genommen kaum von Stubs, für diese führen Sie aber eine Assert-Anweisung aus, und für einen Stub nicht.

## <a name="best-practices"></a>Bewährte Methoden

Achten Sie beim Schreiben von Komponententests darauf, dass diese nicht von der Infrastruktur abhängig sind. Dadurch werden die Tests langsam und fehleranfällig. Diese Abhängigkeiten sollten nur für Integrationstests verwendet werden. Sie können diese Abhängigkeiten in Ihrem Code vermeiden, indem Sie das [Prinzip der expliziten Abhängigkeit](https://deviq.com/explicit-dependencies-principle) und [Dependency Injection](../extensions/dependency-injection.md) einsetzen. Sie können die Komponententests und die Integrationstests in unterschiedlichen Projekten erstellen. Dadurch wird sichergestellt, dass Ihr Komponententestprojekt keine Verweise auf oder Abhängigkeiten von Infrastrukturpaketen aufweist.

### <a name="naming-your-tests"></a>Benennen Ihrer Tests

Der Name Ihres Tests sollte aus drei Teilen bestehen:

- aus dem Namen der Methode, die getestet wird
- aus den Bedingungen, unter denen getestet wird
- aus dem erwarteten Verhalten, wenn das Szenario aufgerufen wird

#### <a name="why"></a>Warum?

- Benennungsstandards sind wichtig, da diese die Absicht des Tests explizit ausdrücken.

Tests sind nicht nur dazu da sicherzustellen, dass Ihr Code funktioniert, sie bieten auch Dokumentation. Sie sollten anhand der Komponententestsammlung in der Lage sein, das Verhalten Ihres Codes abzuleiten, auch wenn Sie nicht den Code selbst ansehen. Wenn Tests fehlschlagen, können Sie zusätzlich genau erkennen, welche Szenarios nicht Ihren Erwartungen entsprechen.

#### <a name="bad"></a>Nicht empfohlen:

[!code-csharp[BeforeNaming](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeNaming)]

#### <a name="better"></a>Empfohlen:

[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="arranging-your-tests"></a>Anordnen Ihrer Tests

**Arrange, Act, Assert** ist ein häufiges Muster beim Ausführen von Komponententests. Dieses Muster besteht aus drei Hauptteilen:

- *Arrange* : Ordnen Sie Ihrer Objekte an, und erstellen und planen Sie diese nach Bedarf.
- *Act* : Führen Sie eine Aktion für ein Objekt durch.
- *Assert* : Überprüfen Sie die ordnungsgemäße Funktionsweise.

#### <a name="why"></a>Warum?

- Durch diese Methode wird ganz klar unterteilt, was unter den Schritten *arrange* und *assert* getestet wird.
- Es ist weniger wahrscheinlich, dass Überprüfungen mit dem „act“-Code vermischt werden.

Die Lesbarkeit ist einer der wichtigsten Punkte beim Schreiben eines Tests. Durch die Aufteilung innerhalb des Tests werden die Abhängigkeiten deutlich, die beim Codeaufruf, der Art und Weise des Codeaufrufs und bei der Überprüfung entstehen. Einige Schritte können zwar möglicherweise kombiniert werden, wodurch die Größe Ihres Tests verringert wird, jedoch liegt das Hauptaugenmerk darauf, den Test besser lesbar zu machen.

#### <a name="bad"></a>Nicht empfohlen:

[!code-csharp[BeforeArranging](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeArranging)]

#### <a name="better"></a>Empfohlen:

[!code-csharp[AfterArranging](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterArranging)]

### <a name="write-minimally-passing-tests"></a>Schreiben von minimal erfolgreichen Tests

Die in einem Komponententest verwendete Eingabe soll so einfach wie möglich gehalten werden, damit das Verhalten, das Sie gerade testen, überprüft werden kann.

#### <a name="why"></a>Warum?

- Tests funktionieren auch nach Änderungen an der Codebasis wahrscheinlicher weiter.
- Das Testverhalten steht im Vordergrund, nicht die Implementierung.

Es ist wahrscheinlicher, dass Tests, die mehr Informationen enthalten, als für das Bestehen erforderlich sind, Fehler verursachen. Dadurch kann die Absicht des Tests weniger eindeutig sein. Wenn Sie Tests schreiben, sollte das Verhalten im Vordergrund stehen. Die Festlegung von zusätzlichen Eigenschaften für Modelle oder die Verwendung von Werten, die nicht 0 (null) sind, wenn es nicht nötig ist, lenkt nur vom gewünschten Ergebnis ab.

#### <a name="bad"></a>Nicht empfohlen:

[!code-csharp[BeforeMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMinimallyPassing)]

#### <a name="better"></a>Empfohlen:

[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="avoid-magic-strings"></a>Vermeiden „magischer“ Zeichenfolgen

Das Benennen von Variablen in Komponententests ist genauso wichtig, wenn nicht noch wichtiger, wie das Benennen von Variablen im Produktionscode. Komponententests sollten keine „magischen“ Zeichenfolgen enthalten.

#### <a name="why"></a>Warum?

- Durch magische Zeichenfolgen sieht es der Leser des Tests womöglich nicht als notwendig an, den Produktionscode zu überprüfen, um herauszufinden, was den Wert besonders macht.
- Sie stellen explizit dar, was Sie *beweisen* möchten und nicht, was Sie versuchen zu *erreichen*.

Magische Zeichenfolgen können den Leser Ihrer Tests verwirren. Wenn eine Zeichenfolge nicht wie gewohnt aussieht, fragt sich der Leser womöglich, warum ein bestimmter Wert für einen Parameter oder Rückgabewert ausgewählt wurde. Dadurch sieht sich der Leser möglicherweise die Implementierungsdetails genauer an und konzentriert sich so nicht mehr auf den Test.

> [!TIP]
> Gehen Sie deshalb so genau wie möglich auf die Absicht ein, wenn Sie Tests schreiben. Im Fall von magischen Zeichenfolgen ist es ein guter Ansatz, diese Werte Kontanten zuzuweisen.

#### <a name="bad"></a>Nicht empfohlen:

[!code-csharp[BeforeMagicString](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMagicString)]

#### <a name="better"></a>Empfohlen:

[!code-csharp[AfterMagicString](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterMagicString)]

### <a name="avoid-logic-in-tests"></a>Vermeiden von Logik in Tests

Wenn Sie Ihre Komponententests schreiben, vermeiden Sie manuelle Zeichenfolgenverkettungen und logische Bedingungen, z.B. `if`, `while`, `for`, `switch` usw.

#### <a name="why"></a>Warum?

- Es ist weniger wahrscheinlich, dass dies zu einem Fehler innerhalb Ihrer Tests führt.
- Konzentrieren Sie sich auf das Endergebnis und weniger auf die Implementierungsdetails.

Wenn Sie Logik in Ihre Testsammlung einfügen, erhöht sich die Wahrscheinlichkeit, dass dies zu einem Fehler führt. Ihre Testsammlung sollte auf keinen Fall einen Fehler enthalten. Sie müssen sich wirklich sicher sein, dass Ihre Tests funktionieren, andernfalls können Sie sich nicht auf diese verlassen. Tests, auf die sie sich nicht verlassen können, haben keinen Nutzen. Wenn ein Test fehlschlägt, sollten Sie merken, dass etwas mit Ihrem Code tatsächlich nicht stimmt, und dass dies nicht ignoriert werden kann.

> [!TIP]
> Wenn Logik in Ihrem Test unvermeidlich scheint, dann erwägen Sie, den Test in zwei oder mehr Tests aufzuteilen.

#### <a name="bad"></a>Nicht empfohlen:

[!code-csharp[LogicInTests](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#LogicInTests)]

#### <a name="better"></a>Empfohlen:

[!code-csharp[AfterTestLogic](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterTestLogic)]

### <a name="prefer-helper-methods-to-setup-and-teardown"></a>Hilfsmethoden statt SetUp und TearDown

Wenn Sie für Ihre Test ein ähnliches Objekt oder einen ähnlichen Zustand benötigen, nutzen Sie anstelle der Attribute `Setup` und `Teardown` (falls vorhanden) lieber eine Hilfsmethode.

#### <a name="why"></a>Warum?

- Weniger Verwirrung beim Lesen der Tests, da der gesamte Code innerhalb der einzelnen Tests sichtbar ist.
- Für den spezifischen Test ist das Risiko geringer, zu viel oder zu wenig einzurichten.
- Geringeres Risiko, den Zustand zwischen Tests freizugeben, was zu unnötigen Abhängigkeiten zwischen diesen führen würde.

In Komponententestframeworks wird `Setup` vor jedem Komponententest innerhalb Ihrer Testsammlung aufgerufen. Während einige diese Methode als nützlich betrachten, führt sie letztendlich doch zu überfrachteten und schwer zu lesenden Tests. Jeder Test hat in der Regel unterschiedliche Anforderungen, damit er ordnungsgemäß funktioniert. Leider werden Sie mit `Setup` gezwungen, exakt dieselben Anforderungen für jeden Test zu verwenden.

> [!NOTE]
> Ab xUnit Version 2.x sind SetUp und TearDown nicht mehr verfügbar.

#### <a name="bad"></a>Nicht empfohlen:

[!code-csharp[BeforeSetup](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeSetup)]

```csharp
// more tests...
```

[!code-csharp[BeforeHelperMethod](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeHelperMethod)]

#### <a name="better"></a>Empfohlen:

[!code-csharp[AfterHelperMethod](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterHelperMethod)]

```csharp
// more tests...
```

[!code-csharp[AfterSetup](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterSetup)]

### <a name="avoid-multiple-asserts"></a>Vermeiden mehrerer Assert-Anweisungen

Wenn Sie Ihre Tests schreiben, versuchen Sie, nur eine Assert-Anweisung pro Test einzuschließen. Allgemeine Ansätze zur Verwendung von nur einer Assert-Anweisung sind die folgenden:

- Erstellen eines separaten Tests für jede Assert-Anweisung
- Verwenden parametrisierter Tests

#### <a name="why"></a>Warum?

- Wenn eine Assert-Anweisung fehlschlägt, werden die darauffolgenden Assert-Vorgänge nicht ausgewertet.
- Es wird sichergestellt, dass Sie nicht mehrere Fälle in Ihren Tests überprüfen.
- Sie erhalten einen Überblick, warum Ihre Tests fehlschlagen.

Wenn mehrere Assert-Anweisungen in einer Testsituation verwendet werden, kann nicht garantiert werden, dass alle Assert-Anweisungen ausgeführt werden. In den meisten Komponententestframeworks wird automatisch angenommen, dass die nachfolgenden Tests fehlschlagen, sobald eine Überprüfung in einem Komponententest fehlschlägt. Dies kann verwirrend sein, da eine Funktion, die eigentlich funktioniert, als fehlgeschlagen angezeigt wird.

> [!NOTE]
> Eine Ausnahme bestätigt die Regel: das Überprüfen eines Objekts In diesem Fall sind mehrere Assert-Anweisungen für jede Eigenschaft kein Problem, denn damit wird sichergestellt, dass sich das Objekt in dem Zustand befindet, den Sie von ihm erwarten.

#### <a name="bad"></a>Nicht empfohlen:

[!code-csharp[BeforeMultipleAsserts](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/before/StringCalculatorTests.cs#BeforeMultipleAsserts)]

#### <a name="better"></a>Empfohlen:

[!code-csharp[AfterMultipleAsserts](../../../samples/snippets/core/testing/unit-testing-best-practices/csharp/after/StringCalculatorTests.cs#AfterMultipleAsserts)]

### <a name="validate-private-methods-by-unit-testing-public-methods"></a>Überprüfen privater Methoden durch Komponententest von öffentlichen Methoden

In den meisten Fällen sollte es nicht nötig sein, eine private Methode zu testen. Private Methoden sind ein Implementierungsdetail. Sie können sich diese wie folgt vorstellen: Private Methoden sind nie isoliert vorhanden. Irgendwann wird eine öffentliche Methode die private Methode als Teil ihrer Implementierung aufrufen. Sie sollten sich über das Endergebnis der öffentlichen Methode Gedanken machen, die die private abruft.

Betrachten Sie folgenden Fall:

```csharp
public string ParseLogLine(string input)
{
    var sanitizedInput = TrimInput(input);
    return sanitizedInput;
}

private string TrimInput(string input)
{
    return input.Trim();
}
```

Möglicherweise versuchen Sie zunächst, einen Test für `TrimInput` zu schreiben, da Sie sicherstellen möchten, dass die Methode wie erwartet funktioniert. Es ist jedoch auch möglich, dass `sanitizedInput` von `ParseLogLine` auf unerwartete Weise manipuliert wird, wodurch das Rendern eines Tests für `TrimInput` nutzlos ist.

Der echte Test sollte für die öffentliche Methode, `ParseLogLine`, ausgeführt werden, denn darum sollten Sie sich letztendlich kümmern.

```csharp
public void ParseLogLine_StartsAndEndsWithSpace_ReturnsTrimmedResult()
{
    var parser = new Parser();

    var result = parser.ParseLogLine(" a ");

    Assert.Equals("a", result);
}
```

Wenn Sie mit diesem Wissen eine private Methode erkennen, suchen Sie nach der öffentlichen Methode, und schreiben Sie Ihre Tests für diese. Nur weil eine private Methode die erwarteten Ergebnisse liefert, bedeutet das nicht, dass das System, das letztendlich die private Methode aufruft, das Ergebnis richtig verwendet.

### <a name="stub-static-references"></a>Statische Verweise für Stub

Ein Komponententest muss das zu testende System vollständig steuern können. Wenn der Produktionscode Aufrufe von statischen Verweisen (z.B. `DateTime.Now`) enthält, kann dies zu Problemen führen. Betrachten Sie folgenden Code:

```csharp
public int GetDiscountedPrice(int price)
{
    if (DateTime.Now.DayOfWeek == DayOfWeek.Tuesday)
    {
        return price / 2;
    }
    else
    {
        return price;
    }
}
```

Wie kann für diesen Code am besten ein Komponententest ausgeführt werden? Sie können beispielsweise folgenden Ansatz ausprobieren:

```csharp
public void GetDiscountedPrice_NotTuesday_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(2, actual)
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(1, actual);
}
```

Sie werden wahrscheinlich schnell merken, dass mit Ihren Tests leider einiges nicht stimmt.

- Wenn die Testsammlung an einem Dienstag ausgeführt wird, ist der zweite Test erfolgreich, der erste schlägt jedoch fehl.
- Wenn die Testsammlung an einem anderen Tag ausgeführt wird, ist der erste Test erfolgreich, der zweite schlägt jedoch fehl.

Sie müssen zur Lösung dieser Probleme eine *Nahtstelle* in Ihren Produktionscode einfügen. Eine Methode ist das Umschließen des zu steuernden Codes mit einer Schnittstelle. Der Produktionscode soll dann von dieser Schnittstelle abhängig sein.

```csharp
public interface IDateTimeProvider
{
    DayOfWeek DayOfWeek();
}

public int GetDiscountedPrice(int price, IDateTimeProvider dateTimeProvider)
{
    if (dateTimeProvider.DayOfWeek() == DayOfWeek.Tuesday)
    {
        return price / 2;
    }
    else
    {
        return price;
    }
}
```

Ihre Testsammlung sieht nun so aus:

```csharp
public void GetDiscountedPrice_NotTuesday_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Monday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(2, actual);
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Tuesday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(1, actual);
}
```

Die Testsammlung hat nun volle Kontrolle über `DateTime.Now` und kann für jeden Wert einen Stub ausführen, wenn die Methode aufgerufen wird.
