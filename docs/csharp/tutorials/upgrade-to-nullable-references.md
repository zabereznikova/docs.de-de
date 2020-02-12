---
title: Upgrade auf Nullable-Verweistypen
description: In diesem erweiterten Tutorial wird veranschaulicht, wie vorhandener Code mit Nullable-Verweistypen migriert wird.
ms.date: 02/19/2019
ms.technology: csharp-null-safety
ms.custom: mvc
ms.openlocfilehash: 4edeab7b2a4211d50c424f567ad7df6ced0bf4ce
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093304"
---
# <a name="tutorial-migrate-existing-code-with-nullable-reference-types"></a>Tutorial: Migrieren vorhandenen Codes mit Verweistypen, die NULL-Werte zulassen

C# 8 führt **Verweistypen, die NULL-Werte zulassen** ein, die Verweistypen auf die gleiche Weise ergänzen, wie NULL-Werte zulassenden Werttypen Werttypen ergänzen. Sie deklarieren eine Variable zu einem **Verweistyp, der NULL-Werte zulässt**, indem Sie `?` an den Typen anfügen. Beispielsweise stellt `string?` eine `string` dar, die NULL-Werte zulässt. Mit diesen neuen Typen können Sie Ihre Entwurfsabsicht besser zum Ausdruck bringen: Einige Variablen *müssen immer einen Wert* haben, bei anderen *kann ein Wert fehlen*. Alle vorhandenen Variablen eines Verweistyps würden als NULL-Werte zulassende Verweistypen interpretiert. 

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> - Aktivieren von NULL-Verweis-Überprüfungen beim Arbeiten mit Code.
> - Diagnostizieren und Korrigieren verschiedener Warnungen im Zusammenhang mit NULL-Werten.
> - Verwalten der Schnittstelle zwischen NULL-Werte zulassenden und NULL-Werte nicht zulassenden Kontexten.
> - Steuern NULL-Werte zulassender Anmerkungskontexte.

## <a name="prerequisites"></a>Voraussetzungen

Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten, einschließlich des C# 8.0-Compilers. Der C# 8-Compiler steht ab [Visual Studio 2019 Version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder mit dem [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) zur Verfügung.

In diesem Tutorial wird vorausgesetzt, dass Sie C# und .NET, einschließlich Visual Studio oder die .NET Core-CLI kennen.

## <a name="explore-the-sample-application"></a>Untersuchen der Beispielanwendung

Die Beispielanwendung, die Sie migrieren, ist eine RSS-Feed-Reader-Web-App. Sie liest aus einem einzelnen RSS-Feed und zeigt Zusammenfassungen für die neuesten Artikel an. Sie können einen der Artikel auswählen, um auf die Website zuzugreifen. Die Anwendung ist relativ neu, wurde jedoch geschrieben, bevor NULL-Werte zulassende Verweistypen verfügbar waren. Die Entwurfsentscheidungen für die Anwendung stellten bewährte Prinzipien dar, nutzen diese wichtige Sprachfunktion jedoch nicht.

Die Beispielanwendung enthält eine Komponententestbibliothek, die die wichtigsten Funktionen der App überprüft. Das Projekt wird die sichere Aktualisierung erleichtern, wenn Sie Teile der Implementierung entsprechend der generierten Warnungen ändern. Sie können den Startercode aus dem Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/nullable-reference-migration/start) auf GitHub herunterladen.

Ihr Ziel beim Migrieren eines Projekts sollte die Nutzung neuer Sprachfeatures sein, sodass Sie deutlich Ihre Absicht bezüglich des Zulassens von NULL-Werten bei Variablen ausdrücken, und zwar so, dass der Compiler keine Warnungen generiert, wenn Sie für den NULL-Werte zulassenden Anmerkungskontext und den NULL-Werte zulassenden Warnungskontext `enabled` festlegen.

## <a name="upgrade-the-projects-to-c-8"></a>Aktualisieren der Projekte auf C# 8

Ein guter erster Schritt ist, den Bereich der Migrationsaufgabe zu bestimmen. Beginnen Sie mit dem Upgrade des Projekts auf C# 8.0 (oder höher). Fügen Sie der PropertyGroup-Eigenschaft das `LangVersion`-Element in beiden CSPROJ-Dateien für das Webprojekt und das Komponententestprojekt hinzu:

```xml
<LangVersion>8.0</LangVersion>
```

Beim Aktualisieren der Sprachversion wird C# 8.0 ausgewählt, aber dies aktiviert nicht den NULL-Werte zulassenden Anmerkungskontext oder den NULL-Werte zulassenden Warnungskontext. Erstellen Sie das Projekt neu, um sicherzustellen, dass es ohne Warnungen erstellt wird.

Ein guter nächster Schritt ist, den NULL-Werte zulassenden Anmerkungskontext zu aktivieren und zu sehen, wie viele Warnungen generiert werden. Fügen Sie das folgende Element beiden CSPROJ-Dateien in der Projektmappe hinzu, direkt unterhalb des `LangVersion`-Elements:

```xml
<Nullable>enable</Nullable>
```

Führen Sie einen Testbuild durch, und beachten Sie die Liste der Warnungen. In dieser kleinen Anwendung generiert der Compiler fünf Warnungen, daher sollten Sie den NULL-Werte zulassenden Anmerkungskontext aktiviert lassen und beginnen, Warnungen für das gesamte Projekt zu beheben.

Diese Strategie funktioniert nur bei kleineren Projekten. Bei größeren Projekten erschwert die Anzahl der Warnungen, die durch das Aktivieren des NULL-Werte zulassenden Anmerkungskontexts für die gesamte Codebase generiert werden, die systematische Behebung der Warnungen. Für größere Enterprise-Projekte müssen Sie häufig jeweils ein Projekt migrieren. In jedem Projekt migrieren Sie jeweils eine Klasse oder eine Datei.

## <a name="warnings-help-discover-original-design-intent"></a>Warnungen tragen dazu bei, die ursprüngliche Entwurfsabsicht zu ermitteln

Es gibt zwei Klassen, die mehrere Warnungen generieren. Beginnen Sie mit der `NewsStoryViewModel`-Klasse. Entfernen Sie das `Nullable`-Element aus beiden CSPROJ-Dateien, damit Sie den Bereich der Warnungen auf die Abschnitte des Codes beschränken können, mit denen Sie arbeiten. Öffnen Sie die *NewsStoryViewModel.cs*-Datei, und fügen Sie die folgenden Anweisungen zum Aktivieren des NULL-Werte zulassenden Anmerkungskontexts für das `NewsStoryViewModel` hinzu, und stellen Sie es nach dieser Klassendefinition wieder her:

```csharp
#nullable enable
public class NewsStoryViewModel
{
    public DateTimeOffset Published { get; set; }
    public string Title { get; set; }
    public string Uri { get; set; }
}
#nullable restore
```

Mit diesen beiden Anweisungen können Sie sich auf Ihre Migration konzentrieren. Die NULL-Werte zulassenden Warnungen werden für den Bereich des Codes generiert, an dem Sie aktiv arbeiten. Sie müssen sie aktiviert lassen, bis Sie bereit sind, die Warnungen für das gesamte Projekt zu aktivieren. Verwenden Sie den Wert `restore` statt `disable`, sodass Sie später nicht versehentlich den Kontext deaktivieren, wenn Sie NULL-Werte zulassende Anmerkungen für das gesamte Projekt aktiviert haben. Nachdem Sie für das gesamte Projekt den NULL-Werte zulassenden Anmerkungskontext aktiviert haben, können Sie alle `#nullable`-Pragmas aus dem Projekt entfernen.

Die `NewsStoryViewModel`-Klasse ist ein Datenübertragungsobjekt (Data Transfer Object, DTO), und zwei der Eigenschaften sind Lese-/Schreibzeichenfolgen:

[!code-csharp[InitialViewModel](~/samples/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/ViewModels/NewsStoryViewModel.cs#StarterViewModel)]

Diese beiden Eigenschaften lösen `CS8618` aus: „Initialisierung der NULL-Werte nicht zulassenden Eigenschaft wird aufgehoben“. Das ist deutlich genug: Beide `string`-Eigenschaften weisen den Standardwert `null` auf, wenn ein `NewsStoryViewModel` erstellt wird. Es ist wichtig, zu ermitteln, wie `NewsStoryViewModel`-Objekte erstellt werden. Wenn Sie diese Klasse betrachten, ist nicht erkennbar, ob der `null`-Wert Teil des Entwurfs ist, oder ob diese Objekte bei ihrer Erstellung auf Werte ungleich Null festgelegt werden. Die neuen Storys werden in der `GetNews`-Methode der `NewsService`-Klasse erstellt:

[!code-csharp[StarterCreateNewsItem](~/samples/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/Services/NewsService.cs#CreateNewsItem)]

Im vorherigen Codeblock ist einiges los. Diese Anwendung verwendet das [AutoMapper](https://automapper.org/)-NuGet-Paket zum Erstellen eines Nachrichtenelements aus einem `ISyndicationItem`. Sie haben festgestellt, dass in dieser einen Anweisung die Nachrichtenelemente erstellt und die Eigenschaften festgelegt werden. Das bedeutet, dass der Entwurf für das `NewsStoryViewModel` angibt, dass diese Eigenschaften nie den Wert `null` haben sollten. Diese Eigenschaften sollten **Nullwerte nicht zulassende Verweistypen** sein. Das drückt am besten die ursprüngliche Entwurfsabsicht aus. Jedes `NewsStoryViewModel` *ist* in der Tat mit Werten ungleich NULL ordnungsgemäß instanziiert. Das macht den folgenden Initialisierungscode zu einer gültigen Fehlerbehebung:

```csharp
public class NewsStoryViewModel
{
    public DateTimeOffset Published { get; set; }
    public string Title { get; set; } = default!;
    public string Uri { get; set; } = default!;
}
```

Die Zuweisung von `Title` und `Uri` zu `default`, die `null` für den `string`-Typ ist, ändert das Laufzeitverhalten des Programms nicht. Das `NewsStoryViewModel` ist immer noch mit NULL-Werten erstellt, aber jetzt gibt der Compiler keine Warnungen aus. Der **NULL-tolerante Operator**, das `!`-Zeichen, das auf den `default`-Ausdruck folgt, teilt dem Compiler mit, dass der vorherige Ausdruck nicht NULL ist. Diese Technik kann zweckmäßig sein, wenn andere Änderungen viel größere Änderungen einer Codebasis erzwingen, aber in dieser Anwendung gibt es eine relativ schnelle und bessere Lösung: Machen Sie das `NewsStoryViewModel` zu einem unveränderlichen Typ, in dem alle Eigenschaften im Konstruktor festgelegt werden. Nehmen Sie am `NewsStoryViewModel` die folgenden Änderungen vor:

[!code-csharp[FinishedViewModel](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/ViewModels/NewsStoryViewModel.cs#FinishedViewModel)]

Sobald das geschehen ist, müssen Sie den Code aktualisieren, der den AutoMapper konfiguriert, sodass er den Konstruktor verwendet, anstatt Eigenschaften festzulegen. Öffnen Sie `NewsService.cs`, und suchen Sie unten in der Datei den folgenden Code:

[!code-csharp[StarterAutoMapper](~/samples/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/Services/NewsService.cs#ConfigureAutoMapper)]

Dieser Code weist Eigenschaften des `ISyndicationItem`-Objekts den `NewsStoryViewModel`-Eigenschaften zu. Sie möchten, dass der AutoMapper die Zuordnung stattdessen mithilfe eines Konstruktors bereitstellt. Ersetzen Sie den obigen Code mit der folgenden Automapper-Konfiguration:

[!code-csharp[FinishedViewModel](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Services/NewsService.cs#ConfigureAutoMapper)]

Beachten Sie: Da diese Klasse klein ist, und Sie sie sorgfältig untersucht haben, sollten Sie die `#nullable enable`-Anweisung über dieser Klassendeklaration aktivieren. Die Änderung am Konstruktor könnte etwas beschädigt haben, darum lohnt es sich, alle Tests auszuführen und die Anwendung zu testen, bevor Sie fortfahren.

Der erste Satz von Änderungen zeigte Ihnen, wie Sie ermitteln, wann der ursprüngliche Entwurf anzeigte, dass für Variablen nicht `null` festgelegt werden sollte. Diese Technik wird als **Korrigieren nach Erstellung** bezeichnet. Sie deklarieren, dass ein Objekt und seine Eigenschaften nicht `null` sein können, wenn es erstellt wird. Die Flussanalyse des Compilers bietet die Gewissheit, dass diese Eigenschaften nach der Erstellung nicht auf `null` gesetzt sind. Beachten Sie, dass dieser Konstruktor durch externen Code aufgerufen wird, und dieser Code **ignoriert NULL-Werte**. Die neue Syntax bietet keine Runtimeüberprüfung. Externer Code könnte die Flussanalyse des Compilers umgehen. 

In anderen Fällen bietet die Struktur einer Klasse andere Hinweise zur Absicht. Öffnen Sie die *Error.cshtml.cs*-Datei im Ordner *Pages*. Das `ErrorViewModel` enthält folgenden Code:

[!code-csharp[StarterErrorModel](~/samples/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/Pages/Error.cshtml.cs#StartErrorModel)]

Fügen Sie die `#nullable enable`-Anweisung vor der Klassendeklaration und eine `#nullable restore`-Anweisung dahinter hinzu. Sie erhalten eine Warnung, das `RequestId` nicht initialisiert ist. Wenn Sie die Klasse betrachten, sollten Sie entscheiden, dass die `RequestId`-Eigenschaft in einigen Fällen NULL sein sollte. Das Vorhandensein der `ShowRequestId`-Eigenschaft gibt an, dass fehlende Werte möglich sind. Da `null` gültig ist, fügen Sie `?` dem `string`-Typ hinzu, um anzugeben, dass die `RequestId`-Eigenschaft ein *NULL-Werte zulassender Verweistyp* ist. Die finale Klasse sieht wie im folgenden Beispiel aus:

[!code-csharp[FinishedErrorModel](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Pages/Error.cshtml.cs#ErrorModel)]

Überprüfen Sie die Verwendung der Eigenschaft, und Sie sehen, dass die Eigenschaft auf der entsprechenden Seite vor dem Rendern im Markup auf NULL überprüft wird. Das ist eine sichere Verwendung eines NULL-Werte zulassenden Verweistyps, also sind Sie mit dieser Klasse fertig.

## <a name="fixing-nulls-causes-change"></a>Beheben von NULL-Werten führt zu Änderungen

In vielen Fällen führt das Beheben einer Reihe von Warnungen in zugehörigem Code zu neuen Warnungen. Sehen wir uns die Warnungen in Aktion durch Beheben der `index.cshtml.cs`-Klasse an. Öffnen Sie die Datei `index.cshtml.cs`, und überprüfen Sie den Code. Diese Datei enthält den Code für die Indexseite:

[!code-csharp[StarterIndexModel](~/samples/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/Pages/Index.cshtml.cs#IndexModelStart)]

Fügen Sie die `#nullable enable`-Anweisung hinzu, und Sie sehen zwei Warnungen. Weder die `ErrorText`-Eigenschaft noch die `NewsItems`-Eigenschaft ist initialisiert. Bei einer Untersuchung dieser Klasse würden Sie zu dem Schluss kommen, dass beide Eigenschaften Nullwerte zulassende Verweistypen sein sollten: Beide haben private Setter. Genau einer wird in der `OnGet`-Methode zugewiesen. Bevor Sie Änderungen vornehmen, betrachten Sie die Benutzer beider Eigenschaften. Auf der Seite selbst wird `ErrorText` vor dem Generieren von Markups für Fehler auf NULL überprüft. Die `NewsItems`-Sammlung wird auf `null` überprüft, und um sicherzustellen, dass die Sammlung Elemente enthält. Eine schnelle Lösung wäre, beide Eigenschaften zu Nullwerte zulassenden Verweistypen zu machen. Eine bessere Lösung wäre, die Sammlung eines Nullwerte nicht zulassenden Verweistyps zu erstellen und beim Abrufen von Nachrichten der vorhandenen Sammlung Elemente hinzuzufügen. Die erste Lösung ist, `?` dem `string`-Typ für den `ErrorText` hinzuzufügen:

[!code-csharp[UpdateErrorText](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Pages/Index.cshtml.cs#UpdateErrorText)]

Diese Änderung würde anderen Code nicht beeinflussen, da jeder Zugriff auf die `ErrorText`-Eigenschaft bereits durch NULL-Überprüfungen geschützt wurde. Initialisieren Sie als Nächstes die `NewsItems`-Liste, und entfernen Sie den Eigenschaftensetter, und machen Sie ihn zu einer schreibgeschützten Eigenschaft:

[!code-csharp[InitializeNewsItems](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Pages/Index.cshtml.cs#InitializeNewsItems)]

Damit wird die Warnung behoben, jedoch ein Fehler eingeführt. Die `NewsItems`-Liste ist nun **korrigiert nach Erstellung**, aber der Code, der die Liste in `OnGet` festlegt, muss der neuen API entsprechend geändert werden. Rufen Sie anstelle einer Zuweisung `AddRange` auf, um die Nachrichtenelemente der vorhandenen Liste hinzuzufügen:

[!code-csharp[AddRange](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Pages/Index.cshtml.cs#AddRange)]

`AddRange` anstelle einer Zuordnung zu verwenden bedeutet, dass die `GetNews`-Methode `IEnumerable` anstelle einer `List` zurückgeben kann. Das spart eine Zuordnung. Ändern Sie die Signatur der Methode, und entfernen Sie den `ToList`-Aufruf, wie im folgenden Codebeispiel gezeigt:

[!code-csharp[GetNews](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Services/NewsService.cs#GetNewsFinished)]

Ändern der Signatur unterbricht auch einen der Tests. Öffnen Sie die `NewsServiceTests.cs`-Datei im `Services`-Ordner des `SimpleFeedReader.Tests`-Projekts. Navigieren Sie zum `Returns_News_Stories_Given_Valid_Uri`-Test, und ändern Sie den Typ der `result`-Variablen in `IEnumerable<NewsItem>`. Ändern des Typs bedeutet, dass die `Count`-Eigenschaft nicht mehr verfügbar ist, also ersetzen Sie die `Count`-Eigenschaft in `Assert` mit einem Aufruf von `Any()`:

[!code-csharp[FixTests](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader.Tests/Services/NewsServiceTests.cs#FixTestSignature)]

Sie müssen ebenfalls eine `using System.Linq`-Anweisung am Anfang der Datei hinzufügen.

Dieser Satz von Änderungen hebt die besondere Berücksichtigung bei der Aktualisierung von Code hervor, der generische Instanziierungen enthält. Die Liste und die Elemente in der Liste sind nicht NULL-Werte zulassende Typen. Die einen oder anderen oder beide könnten NULL-Werte zulassende Typen sein. Alle folgenden Deklarationen sind zulässig:

- `List<NewsStoryViewModel>`: Nullwerte nicht zulassende Liste Nullwerte nicht zulassender Ansichtsmodelle.
- `List<NewsStoryViewModel?>`: Nullwerte nicht zulassende Liste Nullwerte zulassender Ansichtsmodelle.
- `List<NewsStoryViewModel>?`: Nullwerte zulassende Liste Nullwerte nicht zulassender Ansichtsmodelle.
- `List<NewsStoryViewModel?>?`: Nullwerte zulassende Liste Nullwerte zulassender Ansichtsmodelle.

## <a name="interfaces-with-external-code"></a>Schnittstellen mit externem Code

Da Sie Änderungen an der `NewsService`-Klasse vorgenommen haben, aktivieren Sie die `#nullable enable`-Anmerkung für diese Klasse. Dadurch werden keine neuen Warnungen generiert. Eine sorgfältige Prüfung der Klasse könnte jedoch die Veranschaulichung einiger Einschränkungen der Flussanalyse des Compilers erleichtern. Untersuchen Sie den Konstruktor:

[!code-csharp[ServiceConstructor](~/samples/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Services/NewsService.cs#ServiceConstructor)]

Der `IMapper`-Parameter ist als Nullwerte nicht zulassender Verweis typisiert. Er wird vom ASP.NET Core-Infrastrukturcode aufgerufen, sodass der Compiler nicht wirklich weiß, dass der `IMapper` niemals NULL sein wird. Der standardmäßige ASP.NET Core-Abhängigkeitsinjektionscontainer (DI) löst eine Ausnahme aus, wenn er einen notwendigen Dienst nicht auflösen kann, damit der Code korrekt ist. Der Compiler kann nicht alle Aufrufe Ihrer öffentlichen APIs überprüfen, auch wenn der Code mit NULL-Werte zulassenden Anmerkungskontexten kompiliert wird. Darüber hinaus können Ihre Bibliotheken von Projekten genutzt werden, für die die Nutzung NULL-Werte zulassender Verweistypen noch nicht festgelegt ist. Überprüfen Sie die Eingaben in öffentliche APIs, obwohl Sie sie als Nullwerte nicht zulassende Typen deklariert haben.

## <a name="get-the-code"></a>Abrufen des Codes

Da Sie die Warnungen behoben haben, die Sie in der ersten Testkompilierung identifizierten, können Sie jetzt den NULL-Werte zulassenden Anmerkungskontext für beide Projekte aktivieren. Erstellen Sie die Projekte neu; der Compiler gibt keine Warnungen aus. Den Code für das fertige Projekt können Sie im GitHub-Repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/nullable-reference-migration/finished) aufrufen.

Die neuen Features, die NULL-Werte zulassende Verweistypen unterstützen, helfen Ihnen, mögliche Fehler in der Behandlung von `null`-Werten in Ihrem Code zu suchen und zu beheben. Das Aktivieren des NULL-Werte zulassenden Anmerkungskontexts ermöglicht Ihnen, Ihre Entwurfsabsicht auszudrücken: Einige Variablen sollten niemals NULL sein, andere Variablen können NULL-Werte enthalten. Diese Funktionen erleichtern Ihnen, Ihre Entwurfsabsicht zu deklarieren. Auf ähnliche Weise weist der NULL-Werte zulassende Warnungskontext den Compiler an, Warnungen auszugeben, wenn Sie diese Absicht verletzt haben. Diese Warnungen leiten Sie an, Aktualisierungen vorzunehmen, die Ihren Code robuster machen, sodass das Auslösen einer `NullReferenceException` während der Ausführung unwahrscheinlicher wird. Sie können den Rahmen dieser Kontexte steuern, damit Sie sich auf lokale zu migrierende Codebereiche konzentrieren können, während die übrige Codebasis hiervon unberührt bleibt. In der Praxis können Sie diese Migrationsaufgabe als Teil der regelmäßigen Wartung Ihrer Klassen durchführen. Dieses Tutorial veranschaulicht das Verfahren zum Migrieren einer Anwendung zur Verwendung von NULL-Werte zulassenden Verweistypen. Der PR von [Jon Skeet](https://github.com/jskeet) zum Integrieren Nullwerte zulassender Verweistypen in [NodaTime](https://github.com/nodatime/nodatime/pull/1240/commits) bietet Ihnen ein umfangreicheren Beispiel dieses Prozesses aus der realen Welt. Sie können auch zusätzlich Techniken zum Verwenden von Nullable-Verweistypen mit Entity Framework Core unter [Entity Framework Core: Arbeiten mit Nullable-Verweistypen](/ef/core/miscellaneous/nullable-reference-types) erlernen.
