---
title: Pakete, Metapakete und Frameworks
description: Pakete, Metapakete und Frameworks
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 609b0845-49e7-4864-957b-21ffe1b93bf2
translationtype: Human Translation
ms.sourcegitcommit: cb2e83b35b5a4aae14c89bcbdf26b064885a477a
ms.openlocfilehash: 6b5bb7042fdaa453966a4fc576291b3c90ee5410

---

# <a name="packages-metapackages-and-frameworks"></a>Pakete, Metapakete und Frameworks

.NET Core ist eine Plattform, die aus NuGet-Paketen besteht. Einige Produkte profitieren von differenzierten Paketdefinitionen während andere von undifferenzierten profitieren. Um dieser Dualität entgegenzukommen, wird dieses Produkt als eine Gruppe von differenzierten Paketen verteilt und dann in undifferenzierteren Blöcken mit einem Pakettyp beschrieben, der informell als „Metapaket“ bekannt ist.

Jedes .NET Core-Paket unterstützt die Ausführung auf mehreren als Framework dargestellten .NET-Laufzeiten. Einige dieser Frameworks sind traditionelle Frameworks, wie z.B. `net46`, das das .NET Framework darstellt. Eine andere Gruppe sind neue Frameworks, die man sich als „paketbasierte Frameworks“ vorstellen kann, die ein neues Modell zum Definieren von Frameworks einführen. Diese paketbasierten Frameworks sind vollständig als Pakete formuliert und definiert, und bilden dadurch eine starke Beziehung zwischen Paketen und Frameworks.

## <a name="packages"></a>Pakete

.NET Core ist in verschiedene Pakete aufgeteilt, die Primitive, Datentypen der höheren Ebene, Anwendungskompositionstypen und allgemeine Hilfsprogramme bereitstellen. Jedes dieser Pakete stellt eine einzelne Assembly mit dem gleichen Namen dar. [System.Runtime](https://www.nuget.org/packages/System.Runtime) enthält z.B. System.Runtime.dll. 

Es gibt Vorteile zum Definieren von Paketen in differenzierter Weise:

- Differenzierte Pakete können gemäß ihrem eigenen Zeitplan mit relativ wenigen Tests von anderen Paketen geliefert werden.
- Differenzierte Pakete können unterschiedliche Betriebssysteme und CPU-Support bieten.
- Differenzierte Pakete können über Abhängigkeiten verfügen, die spezifisch zu nur einer Bibliothek sind.
- Apps sind kleiner, da Pakete, auf die nicht verwiesen wird, kein Teil der App-Verteilung werden.

Manche dieser Vorteile werden nur unter bestimmten Umständen verwendet. NET Core-Pakete werden z.B. in der Regel nach demselben Zeitplan mit der gleichen Plattformunterstützung geliefert. Bei der Wartung können Korrekturen als kleine Updates in einem einzigen Paket geliefert und installiert werden. Aufgrund des engen Rahmens für Änderungen ist die Überprüfung und Zeit, bis eine Korrektur verfügbar ist, auf die Zeit eingeschränkt, die für eine einzelne Bibliothek benötigt wir.

Im Folgenden werden die Haupt-NuGet-Pakete für .NET Core aufgelistet:

- [System.Runtime](https://www.nuget.org/packages/System.Runtime) – das wichtigste .NET Core-Paket einschließlich [Objekt](http://docs.microsoft.com/dotnet/core/api/System.Object), [Zeichenfolge](http://docs.microsoft.com/dotnet/core/api/System.String), [Array](http://docs.microsoft.com/dotnet/core/api/System.Array), [Aktion](http://docs.microsoft.com/dotnet/core/api/System.Action) und [IList&lt;T&gt;](http://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IList-1).
- [System.Collections](https://www.nuget.org/packages/System.Collections) – eine Reihe von (primär) generischen Auflistungen, einschließlich [Liste&lt;T&gt;](http://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) und [Wörterbuch&lt;K,V&gt;](http://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2).
- [System.Net.Http](https://www.nuget.org/packages/System.Net.Http) – eine Reihe von Typen für die HTTP-Netzwerkkommunikation, einschließlich [HttpClient](http://docs.microsoft.com/dotnet/core/api/System.Net.Http.HttpClient) und [HttpResponseMessage](http://docs.microsoft.com/dotnet/core/api/System.Net.Http.HttpResponseMessage).
- [System.IO.FileSystem](https://www.nuget.org/packages/System.IO.FileSystem) – eine Reihe von Typen zum Lesen und Schreiben in lokale oder datenträgerbasierte Speicher in Netzwerken, einschließlich [Datei](http://docs.microsoft.com/dotnet/core/api/System.IO.File) und [Verzeichnis](http://docs.microsoft.com/dotnet/core/api/System.IO.Directory).
- [System.Linq](https://www.nuget.org/packages/System.Linq) – eine Reihe von Typen zur Abfrage von Objekten, einschließlich Enumerable und [ILookup&lt;TKey, TElement&gt;](http://docs.microsoft.com/dotnet/core/api/System.Linq.ILookup-2).
- [System.Reflection](https://www.nuget.org/packages/System.Reflection) – eine Reihe von Typen für das Laden, Überprüfen und Aktivieren von Typen, einschließlich [Assembly](http://docs.microsoft.com/dotnet/core/api/System.Reflection.Assembly), [TypeInfo](http://docs.microsoft.com/dotnet/core/api/System.Reflection.TypeInfo) und [MethodInfo](http://docs.microsoft.com/dotnet/core/api/System.Reflection.MethodInfo).

Auf Pakete wird in „project.json“ verwiesen. Im folgenden Beispiel wird auf das [System.Runtime](https://www.nuget.org/packages/System.Runtime/) Paket verwiesen. 

```json
{
  "dependencies": {
    "System.Runtime": "4.1.0"
  },
  "frameworks": {
    "netstandard1.6": {}
  }
}
```

In den meisten Fällen werden Sie nicht direkt auf .NET Core-Pakete der niedrigerer Ebene verweisen, da dies zu viele Pakete ergeben würde, die verwaltet werden müssen. Stattdessen müssen Sie auf ein Metapaket verweisen.

## <a name="metapackages"></a>Metapakete

Metapakete sind eine NuGet-Paket-Konvention zur Beschreibung einer Reihe von Paketen, die zusammen sinnvoll sind. Sie stellen diese Reihe von Paketen dar, indem Sie sie zu Abhängigkeiten machen. Sie können optional ein Framework für diesen Satz von Paketen einrichten, indem Sie ein Framework angeben. 

Durch das Verweisen auf ein Metapaket fügen Sie tatsächlich in einer einzigen Geste einen Verweis auf jedes einzelne abhängige Paket hinzu. Das bedeutet, dass alle Bibliotheken in diesen Paketen (Refs oder Libs) für IntelliSense (oder ähnliches) und für die Veröffentlichung (nur Libs) Ihrer App verfügbar sind. 

Hinweis: Die Begriffe „Lib“ und „Ref“ beziehen sich auf Ordner in NuGet-Paketen. In den Ordnern „Ref“ wird die öffentliche API eines Pakets über Assemblymetadaten beschrieben. Die Ordner „Lib“ enthalten die Implementierung dieser öffentlichen API für ein bestimmtes Framework. 

Es gibt Vorteile gegenüber der Verwendung von Metapaketen:

- Ermöglicht benutzerfreundliches Verweisen auf eine große Zahl von differenzierten Paketen. 
- Definiert eine Reihe von Paketen (einschließlich spezifischer Versionen), die getestet werden, und die gut zusammen funktionieren.

Das .NET Standardbibliothek-Metapaket:

- [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) – beschreibt die Bibliotheken, die Teil der „.NET Standardbibliothek“ sind. Gilt für alle .NET-Implementierungen (z.B. .NET Framework, .NET Core und Mono), die die .NET-Standardbibliothek unterstützen. Legt das Framework „netstandard“ fest.

Das sind die Haupt-.NET Core-Metapakete:

- [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App) – beschreibt die Bibliotheken, die Teil der .NET Core Verteilung sind. Richtet das[`.NETCoreApp` Framework](https://github.com/dotnet/core-setup/blob/master/pkg/projects/Microsoft.NETCore.App/Microsoft.NETCore.App.pkgproj) ein. Dies ist abhängig von der kleineren `NETStandard.Library`.
- [Microsoft.NETCore.Portable.Compatibility](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility) – eine Reihe von Kompatibilitätsfassaden, mit denen mscorlib-basierte Portable Klassenbibliotheken (Portable Class Libraries, PCLs) auf .NET Core ausgeführt werden können.

In „project.json“ wird auf Metapakete sowie andere NuGet-Pakete verwiesen. 

Im folgenden Beispiel wird auf das Metapaket `NETStandard.Library` verwiesen, das zum Erstellen von Bibliotheken verwendet wird, die zwischen .NET-Laufzeiten portabel sind.

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  },
  "frameworks": {
    "netstandard1.6": {}
  }
}
```

Im folgenden Beispiel wird auf das Metapaket `Microsoft.NETCore.App` verwiesen, das zum Erstellen von Anwendungen und Bibliotheken verwendet wird, die dazu vorgesehen sind, auf .NET Core ausgeführt zu werden und die gesamten Vorteile zu nutzen. Es ermöglicht den Zugriff auf einen größeren Satz von Bibliotheken als von der `NETStandard.Library` bereitgestellt werden.

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.0"
  },
  "frameworks": {
    "netcoreapp1.0": {}
  }
}
```

## <a name="frameworks"></a>Frameworks

.NET Core-Pakete unterstützen alle eine Gruppe von Frameworks, die mit Framework-Ordnern (innerhalb der vorher erwähnten Ordner „Lib“ und „Ref“) deklariert werden. Frameworks beschreiben einen zur Verfügung stehenden API-Satz (und mögliche andere Eigenschaften), auf den Sie sich verlassen können, wenn Sie ein bestimmtes Framework als Ziel festlegen. Sie werden mit Versionsangabe versehen, wenn neue APIs hinzugefügt werden.

[System.IO.FileSystem](https://www.nuget.org/packages/System.IO.FileSystem) unterstützt z.B. die folgenden Frameworks:

- .NETFramework,Version=4.6
- .NETStandard,Version=1.3
- 6 Xamarin-Plattformen (z.B. xamarinios10)

Es ist hilfreich, die ersten beiden dieser Frameworks zu vergleichen, da diese ein Beispiel für die zwei verschiedenen Arten sind, wie Frameworks definiert werden.

Das Framework `.NETFramework,Version=4.6` stellt die in .NET Framework 4.6 verfügbaren APIs dar. Sie können Bibliotheken erzeugen, die mit .NET Framework 4.6-Verweisassemblys kompiliert sind, und diese Bibliotheken dann in NuGet-Paketen in einem „net46 lib“-Ordner verteilen. Sie werden für Apps verwendet, die .NET Framework 4.6. als Ziel haben oder damit kompatibel sind. Auf diese Weise haben bisher alle Frameworks gearbeitet.

Das Framework `.NETStandard,Version=1.3` ist ein paketbasiertes Framework. Es verlässt sich auf Pakete, die das Framework als Ziel haben, um APIs zu definieren und in Bezug auf das Framework verfügbar zu machen.

## <a name="package-based-frameworks"></a>Paketbasierte Frameworks

Es besteht eine bidirektionale Beziehung zwischen Frameworks und Paketen. Der erste Teil definiert die APIs, die für ein angegebenes Framework verfügbar sind, z.B. `netstandard1.3`. Pakete, die `netstandard1.3` (oder kompatible Frameworks wie `netstandard1.0`) als Ziel haben, definieren die APIs, die für `netstandard1.3` verfügbar sind. Das hört sich möglicherweise wie eine zirkuläre Definition an, das ist aber nicht der Fall. Aufgrund ihrer Eigenschaft „paketbasiert“ stammt die API-Definition für das Framework aus Paketen. Das Framework selbst definiert keine APIs.

Der zweite Teil der Beziehung ist die Auswahl von Ressourcen. Pakete können Ressourcen für mehrere Frameworks enthalten. Bei einem Verweis auf eine Gruppe von Paketen und/oder Metapaketen ist das Framework erforderlich, um zu bestimmen, welche Ressource ausgewählt werden sollen, z.B. `net46` oder `netstandard1.3`. Es ist wichtig, dass Sie die richtige Ressource auswählen. Eine `net46`-Ressource zum Beispiel ist wahrscheinlich nicht mit .NET Framework 4.0 oder .NET Core 1.0 kompatibel.

![Paketbasierte Framework-Komposition](./media/packages/package-framework.png)

Sie können diese Beziehung in der Abbildung oben sehen. Die *API* hat das *Framework* als Ziel und definiert es. Das *Framework* wird zur *Ressourcenauswahl* verwendet. Von der *Ressource* erhalten Sie die API.

Es ist eine interessante Frage, wo die Definition eines paketbasierten Frameworks endet und die Nutzung dieser Definition beginnt. Man könnte Ihre Ansicht des Frameworks als eine Funktion einer bestimmten „project.json“-Datei ansehen. Ihre Abhängigkeiten erstellen Ihre Ansicht des Frameworks, unabhängig von dem oder den Herausgeber(n) dieser Abhängigkeiten.

Die beiden primären paketbasierten Frameworks, die innerhalb .NET Core verwendet werden, sind:

- `netstandard`
- `netcoreapp`

### <a name="net-standard"></a>.NET Standard

Das Framework .NET Standard (TFM: `netstandard`) stellt die APIs dar, die von der [.NET Standardbibliothek](../standard/library.md) definiert werden und auf dieser basieren. Bibliotheken, die auf mehreren Laufzeiten ausgeführt werden sollen, sollten dieses Framework als Ziel haben. Sie werden auf jeder mit .NET Standard kompatiblen Laufzeit, z.B. .NET Core, .NET Framework und Mono/Xamarin unterstützt. Jede dieser Laufzeiten unterstützt eine Reihe von .NET Standardversionen, je nachdem, welche APIs sie implementieren. 

Das Metapaket `NETStandard.Library` hat das Framework `netstandard` als Ziel. Die gängigste Methode, `netstandard` als Ziel auszuwählen, ist das Verweisen auf dieses Metapaket. Es beschreibt und bietet Zugriff auf etwa 40 .NET-Bibliotheken und zugehörige APIs, die die .NET-Standardbibliothek definieren. Sie können auf zusätzliche Pakete verweisen, die `netstandard` als Ziel haben, um Zugriff auf zusätzliche APIs zu erhalten.

Eine [NETStandard.Library-Version](versions/index.md) entspricht der höchsten `netstandard`-Version, die sie (über dessen Abschluss) verfügbar macht. Die Framework-Referenz in „project.json“ wird verwendet, um die richtigen Ressourcen aus den zugrunde liegenden Paketen auszuwählen. In diesem Fall werden die Ressourcen `netstandard1.6` benötigt, im Gegensatz zu z.B. `netstandard1.4` oder `net46`. 

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  },
  "frameworks": {
    "netstandard1.6": {}
  }
}
```

Das Framework und das Metapaket, auf die in „project.json“ verwiesen wird, müssen nicht übereinstimmen. Zum Beispiel ist die folgende Datei „project.json“ gültig.

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  },
  "frameworks": {
    "netstandard1.3": {}
  }
}
```

Es mag merkwürdig erscheinen, `netstandard1.3` als Ziel festzulegen, aber die 1.6.0-Version von `NETStandard.Library` zu verwenden. Es ist ein gültiger Anwendungsfall, da das Metapaket auch ältere Versionen von `netstandard` unterstützt. Möglicherweise ist es der Fall, dass Sie sich auf Version 1.6.0 des Metapakets standardisiert haben und es für alle Ihre Bibliotheken verwenden, die eine Vielzahl von `netstandard`-Versionen als Ziel haben. Bei diesem Ansatz müssen Sie nur `NETStandard.Library` 1.6.0 wiederherstellen, keine früheren Versionen. 

Das Gegenteil wäre nicht gültig: `netstandard1.6` mit der 1.3.0 Version von `NETStandard.Library` als Ziel festzulegen. Sie können kein höheres Framework mit einem niedrigeren Metapaket als Ziel festlegen, da das Metapaket einer niedrigeren Version keine Ressourcen für dieses höhere Framework verfügbar macht. Das [Versionsschema] für Metapakete bestätigt, dass Metapakete mit der höchsten Version des Frameworks übereinstimmen, das sie beschreiben. Aufgrund des Versionsschemas ist v1.6.0 die erste Version von `NETStandard.Library`, da sie `netstandard1.6`-Ressourcen enthält. v1.3.0 wird im obigen Beispiel für die Symmetrie mit dem obigen Beispiel verwendet, ist aber tatsächlich nicht vorhanden.

### <a name="net-core-application"></a>.NET Core-Anwendung

Das Framework der .NET Core-Anwendung (TFM: `netcoreapp`) stellt die Pakete und die zugehörigen APIs dar, die in der .NET Core-Verteilung enthalten sind, sowie das Konsolenanwendungsmodell, das es bereitstellt. .NET Core-Anwendungen müssen dieses Framework verwenden, da Sie das Konsolenanwendungsmodell als Ziel haben. Bibliotheken, die nur für die Ausführung auf .NET Core vorgesehen waren, sollten dies ebenfalls tun. Die Verwendung dieser Frameworks schränkt Apps und Bibliotheken so ein, dass Sie nur noch auf .NET Core ausgeführt werden können. 

Das Metapaket `Microsoft.NETCore.App` hat das Framework `netcoreapp` als Ziel. Es bietet Zugriff auf ~60-Bibliotheken, ~40 werden durch das `NETStandard.Library`-Paket bereitgestellt, und ~20 weitere werden zusätzlich bereitgestellt. Sie können auf zusätzliche Bibliotheken verweisen, die `netcoreapp` oder kompatible Frameworks wie z.B. `netstandard` als Ziel haben, um den Zugriff auf zusätzliche APIs zu erhalten. 

Die meisten der zusätzlichen Bibliotheken, die von `Microsoft.NETCore.App` bereitgestellt werden, haben ebenfalls `netstandard` als Ziel, vorausgesetzt, dass ihre Abhängigkeiten von anderen `netstandard`-Bibliotheken erfüllt werden. Dies bedeutet, dass `netstandard`-Bibliotheken auch auf diese Pakete als Abhängigkeiten verweisen können. 


<!--HONumber=Nov16_HO3-->


