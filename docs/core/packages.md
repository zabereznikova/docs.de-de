---
title: '.NET Core: Pakete, Metapakete und Frameworks'
description: Lernen Sie die Terminologie für Pakete, Metapakete und Frameworks.
author: richlander
ms.date: 04/29/2020
ms.openlocfilehash: a6575226feb71b96f1fe5070406c118081a8cbf0
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595584"
---
# <a name="packages-metapackages-and-frameworks"></a>Pakete, Metapakete und Frameworks

.NET Core ist eine Plattform, die aus NuGet-Paketen besteht. Einige Produkte profitieren von differenzierten Paketdefinitionen während andere von undifferenzierten profitieren. .NET Core wird zunächst als eine Gruppe von differenzierten Paketen und dann in undifferenzierteren Blöcken mit einem Pakettyp verteilt, der informell als [Metapaket](#metapackages) bezeichnet wird, um dieser Dualität entgegenzukommen.

Jedes .NET Core-Paket unterstützt die Ausführung in mehreren als Framework dargestellten .NET-Implementierungen. Einige dieser Frameworks sind traditionelle Frameworks wie beispielsweise das Framework `net46`, das das .NET Framework darstellt. Eine andere Gruppe sind neue Frameworks, die man sich als „paketbasierte Frameworks“ vorstellen kann, die ein neues Modell zum Definieren von Frameworks einführen. Diese paketbasierten Frameworks werden vollständig als Pakete erstellt und definiert und bilden dadurch eine starke Beziehung zwischen Paketen und Frameworks.

## <a name="packages"></a>Pakete

.NET Core ist in verschiedene Pakete aufgeteilt, die Primitive, Datentypen der höheren Ebene, Anwendungskompositionstypen und allgemeine Hilfsprogramme bereitstellen. Jedes dieser Pakete stellt eine einzelne Assembly mit dem gleichen Namen dar. Das Paket [System.Runtime](https://www.nuget.org/packages/System.Runtime) enthält z. B. System.Runtime.dll.

Es gibt Vorteile zum Definieren von Paketen in differenzierter Weise:

- Differenzierte Pakete können gemäß ihrem eigenen Zeitplan mit relativ wenigen Tests von anderen Paketen geliefert werden.
- Differenzierte Pakete können unterschiedliche Betriebssysteme und CPU-Support bieten.
- Differenzierte Pakete können über Abhängigkeiten verfügen, die spezifisch zu nur einer Bibliothek sind.
- Apps sind kleiner, da Pakete, auf die nicht verwiesen wird, kein Teil der App-Verteilung werden.

Manche dieser Vorteile werden nur unter bestimmten Umständen verwendet. NET Core-Pakete werden z.B. in der Regel nach demselben Zeitplan mit der gleichen Plattformunterstützung geliefert. Bei der Wartung können Korrekturen als kleine Updates in einem einzigen Paket geliefert und installiert werden. Aufgrund des engen Rahmens für Änderungen ist die Überprüfung und Zeit, bis eine Korrektur verfügbar ist, auf die Zeit eingeschränkt, die für eine einzelne Bibliothek benötigt wir.

Im Folgenden werden die Haupt-NuGet-Pakete für .NET Core aufgelistet:

- [System.Runtime](https://www.nuget.org/packages/System.Runtime): das wichtigste .NET Core-Paket, einschließlich <xref:System.Object>, <xref:System.String>, <xref:System.Array>, <xref:System.Action> und <xref:System.Collections.Generic.IList%601>.
- [System.Collections](https://www.nuget.org/packages/System.Collections): ein Reihe von (primär) generischen Auflistungen, einschließlich <xref:System.Collections.Generic.List%601> und <xref:System.Collections.Generic.Dictionary%602>.
- [System.Net.Http](https://www.nuget.org/packages/System.Net.Http): eine Reihe von Typen für die HTTP-Netzwerkkommunikation, einschließlich <xref:System.Net.Http.HttpClient> und <xref:System.Net.Http.HttpResponseMessage>.
- [System.IO.FileSystem](https://www.nuget.org/packages/System.IO.FileSystem): eine Reihe von Typen zum Lesen und Schreiben in lokalen Speicher oder datenträgerbasierten Speicher in Netzwerken, einschließlich <xref:System.IO.File> und <xref:System.IO.Directory>.
- [System.Linq](https://www.nuget.org/packages/System.Linq): eine Reihe von Typen zur Abfrage von Objekten, einschließlich `Enumerable` und <xref:System.Linq.ILookup%602>.
- [System.Reflection](https://www.nuget.org/packages/System.Reflection): eine Reihe von Typen für das Laden, Untersuchen und Aktivieren von Typen, einschließlich <xref:System.Reflection.Assembly>, <xref:System.Reflection.TypeInfo> und <xref:System.Reflection.MethodInfo>.

In der Regel ist es einfacher und stabiler, ein [Metapaket](#metapackages) einzubinden – als ein Paket. Wenn Sie ein einzelnes Paket benötigen, können Sie es wie im folgenden Beispiel einschließen. Das Beispiel verweist auf das [System.Runtime](https://www.nuget.org/packages/System.Runtime/)-Paket.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.6</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

## <a name="metapackages"></a>Metapakete

Ein Metapaket ist eine NuGet-Paketkonvention zur Beschreibung einer Reihe von Paketen, die zusammen sinnvoll sind. Ein Metapaket stellt diese Reihe von Paketen dar, indem sie zu Abhängigkeiten gemacht werden. Das Metapaket kann optional ein Framework für diese Pakete einrichten, indem ein Framework angeben wird.

Frühere Versionen von .NET Core-Tools (*project.json* und *\*CSPROJ*-basierte Tools) geben standardmäßig ein Framework und ein Metapaket an. Derzeit verweist das Zielframework jedoch implizit auf das Metapaket, damit jedes Metapaket mit einem Zielframework verknüpft ist. Zum Beispiel verweist das `netstandard1.6`-Framework auf Version 1.6.0 des Metapakets „NETStandard.Library“. Das `netcoreapp2.1`-Framework verweist in ähnlicher Art und Weise auf das Metapaket der Version 2.1.0 der Microsoft.NETCore.App. Weitere Informationen finden Sie unter [Impliziter Metapaketverweis in .NET Core SDK](https://github.com/dotnet/core/blob/master/release-notes/1.0/sdk/1.0-rc3-implicit-package-refs.md).

Durch das Abzielen auf ein Framework und das implizite Verweisen auf ein Metapaket fügen Sie tatsächlich in einer einzigen Geste einen Verweis auf jedes einzelne abhängige Paket hinzu. Alle Bibliotheken in diesen Paketen sind für IntelliSense (oder ähnliches) und für die Veröffentlichung Ihrer Anwendung verfügbar.

Es gibt Vorteile gegenüber der Verwendung von Metapaketen:

- Ermöglicht benutzerfreundliches Verweisen auf eine große Zahl von differenzierten Paketen.
- Definiert eine Reihe von Paketen (einschließlich spezifischer Versionen), die getestet werden, und die gut zusammen funktionieren.

Das .NET-Standard-Metapaket lautet:

- [NETStandard.Library:](https://www.nuget.org/packages/NETStandard.Library) Dies beschreibt die Bibliotheken, die Teil von .NET Standard sind. Dies gilt für alle .NET-Implementierungen (z. B. .NET Framework, .NET Core und Mono), die .NET-Standard unterstützen. Damit wird das `netstandard`-Framework eingerichtet.

Das sind die .NET Core-Hauptmetapakete:

- [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App) – beschreibt die Bibliotheken, die Teil der .NET Core Verteilung sind. Damit wird das `.NETCoreApp`-Framework eingerichtet. Dies ist abhängig von der kleineren `NETStandard.Library`.
- [Microsoft.AspNetCore.App](https://www.nuget.org/packages/Microsoft.AspNetCore.App): Enthält alle unterstützten Pakete von ASP.NET Core und Entity Framework Core mit Ausnahme derjenigen, die Drittanbieterabhängigkeiten aufweisen. Weitere Informationen finden Sie unter [Microsoft.AspNetCore.App-Metapaket für ASP.NET Core](/aspnet/core/fundamentals/metapackage-app).
- [Microsoft.AspNetCore.All:](https://www.nuget.org/packages/Microsoft.AspNetCore.All) Enthält alle unterstützten Pakete von ASP.NET Core, Entity Framework Core und interne Abhängigkeiten sowie Drittanbieterabhängigkeiten, die von ASP.NET Core und Entity Framework Core verwendet werden. Weitere Informationen finden Sie unter [Das Metapaket „Microsoft.AspNetCore.All“ für ASP.NET Core 2.x](/aspnet/core/fundamentals/metapackage).
- [Microsoft.NETCore.Portable.Compatibility](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility) – eine Reihe von Kompatibilitätsfassaden, mit denen mscorlib-basierte Portable Klassenbibliotheken (Portable Class Libraries, PCLs) auf .NET Core ausgeführt werden können.

## <a name="frameworks"></a>Frameworks

.NET Core-Pakete unterstützen jeweils einen Satz an Laufzeit-Frameworks. Frameworks beschreiben einen zur Verfügung stehenden API-Satz (und mögliche andere Eigenschaften), auf den Sie sich verlassen können, wenn Sie ein bestimmtes Framework als Ziel festlegen. Sie werden mit Versionsangabe versehen, wenn neue APIs hinzugefügt werden.

[System.IO.FileSystem](https://www.nuget.org/packages/System.IO.FileSystem) unterstützt z.B. die folgenden Frameworks:

- .NETFramework,Version=4.6
- .NETStandard,Version=1.3
- 6 Xamarin-Plattformen (z.B. xamarinios10)

Es ist hilfreich, die ersten beiden dieser Frameworks zu vergleichen, da diese ein Beispiel für die zwei verschiedenen Arten sind, wie Frameworks definiert werden:

- Das Framework `.NETFramework,Version=4.6` stellt die in .NET Framework 4.6 verfügbaren APIs dar. Sie können Bibliotheken erstellen, die mit .NET Framework 4.6-Verweisassemblys kompiliert sind, und diese Bibliotheken dann in NuGet-Paketen in einem „net46 lib“-Ordner verteilen. Sie werden für Apps verwendet, die .NET Framework 4.6. als Ziel haben oder damit kompatibel sind. Auf diese Weise haben bisher alle Frameworks gearbeitet.

- Das Framework `.NETStandard,Version=1.3` ist ein paketbasiertes Framework. Es verlässt sich auf Pakete, die das Framework als Ziel haben, um APIs zu definieren und in Bezug auf das Framework verfügbar zu machen.

## <a name="package-based-frameworks"></a>Paketbasierte Frameworks

Es besteht eine bidirektionale Beziehung zwischen Frameworks und Paketen. Der erste Teil definiert die APIs, die für ein angegebenes Framework verfügbar sind, z.B. `netstandard1.3`. Pakete, die `netstandard1.3` (oder kompatible Frameworks wie `netstandard1.0`) als Ziel haben, definieren die APIs, die für `netstandard1.3` verfügbar sind. Das hört sich möglicherweise wie eine zirkuläre Definition an, das ist aber nicht der Fall. Aufgrund ihrer Eigenschaft „paketbasiert“ stammt die API-Definition für das Framework aus Paketen. Das Framework selbst definiert keine APIs.

Der zweite Teil der Beziehung ist die Auswahl von Ressourcen. Pakete können Ressourcen für mehrere Frameworks enthalten. Bei einem Verweis auf eine Gruppe von Paketen und/oder Metapaketen ist das Framework erforderlich, um zu bestimmen, welche Ressource ausgewählt werden sollen, z.B. `net46` oder `netstandard1.3`. Es ist wichtig, dass Sie die richtige Ressource auswählen. Eine `net46`-Ressource zum Beispiel ist wahrscheinlich nicht mit .NET Framework 4.0 oder .NET Core 1.0 kompatibel.

Sie können diese Beziehung in der folgenden Abbildung sehen. Die *API* hat das *Framework* als Ziel und definiert es. Das *Framework* wird zur *Ressourcenauswahl* verwendet. Von der *Ressource* erhalten Sie die API.

![Paketbasierte Framework-Komposition](./media/packages/package-framework.png)

Die beiden primären paketbasierten Frameworks, die innerhalb .NET Core verwendet werden, sind:

- `netstandard`
- `netcoreapp`

### <a name="net-standard"></a>.NET-Standard

Das .NET Standard-Framework ([Zielframeworkmoniker (TFM)](../standard/frameworks.md): `netstandard`) repräsentiert die APIs, die von [.NET Standard](../standard/net-standard.md) definiert werden und darauf basieren. Bibliotheken, die auf mehreren Laufzeiten ausgeführt werden sollen, sollten dieses Framework als Ziel haben. Sie werden auf jeder mit .NET Standard kompatiblen Laufzeit, z. B. .NET Core, .NET Framework und Mono/Xamarin unterstützt. Jede dieser Laufzeiten unterstützt eine Reihe von .NET Standardversionen, je nachdem, welche APIs sie implementieren.

Das `netstandard`-Framework verweist implizit auf die Metapakete [`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library). Die folgende MSBuild-Projektdatei gibt beispielsweise an, dass das Projekt auf `netstandard1.6` abzielt, das auf das Metapaket [`NETStandard.Library` Version 1.6](https://www.nuget.org/packages/NETStandard.Library/1.6.0) verweist.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.6</TargetFramework>
  </PropertyGroup>
</Project>
```

Wenn Sie der Projektdatei das `<NetStandardImplicitPackageVersion>`-Element hinzufügen, das implizit eine Metapaketversion angibt, können Sie eine Frameworkversion angeben, die niedriger als die Metapaketversion ist. Das `<NetStandardImplicitPackageVersion>`-Element ist nur anwendbar, wenn .NET Core und .NET Standard als Ziel verwendet werden. Zum Beispiel ist die folgende Projektdatei gültig.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

Es mag merkwürdig erscheinen, `netstandard1.3` als Ziel festzulegen, aber die 1.6.0-Version von `NETStandard.Library` zu verwenden. Es ist ein gültiger Anwendungsfall, da das Metapaket auch ältere Versionen von `netstandard` unterstützt. Möglicherweise ist es der Fall, dass Sie sich auf Version 1.6.0 des Metapakets standardisiert haben und es für alle Ihre Bibliotheken verwenden, die eine Vielzahl von `netstandard`-Versionen als Ziel haben. Bei diesem Ansatz müssen Sie nur `NETStandard.Library` 1.6.0 wiederherstellen, keine früheren Versionen.

Das Gegenteil wäre nicht gültig: `netstandard1.6` mit der 1.3.0 Version von `NETStandard.Library` als Ziel festzulegen. Sie können kein höheres Framework mit einem niedrigeren Metapaket als Ziel festlegen, da das Metapaket einer niedrigeren Version keine Ressourcen für dieses höhere Framework verfügbar macht. Das Versionsschema für Metapakete bestätigt, dass Metapakete mit der höchsten Version des Frameworks übereinstimmen, das sie beschreiben. Aufgrund des Versionsschemas ist v1.6.0 die erste Version von `NETStandard.Library`, da sie `netstandard1.6`-Ressourcen enthält. (Für die Symmetrie mit dem vorherigen Beispiel wird hier v1.3.0 verwendet, obwohl es nicht wirklich vorhanden ist.)

### <a name="net-core-application"></a>.NET Core-Anwendung

Das .NET Core-Framework ([TFM](../standard/frameworks.md): `netcoreapp`) stellt die Pakete und die zugehörigen APIs dar, die in der .NET Core-Verteilung enthalten sind, sowie das Konsolenanwendungsmodell, das es bereitstellt. .NET Core-Anwendungen müssen dieses Framework verwenden, da Sie das Konsolenanwendungsmodell als Ziel haben. Bibliotheken, die nur für die Ausführung auf .NET Core vorgesehen waren, sollten dies ebenfalls tun. Die Verwendung dieser Frameworks schränkt Apps und Bibliotheken so ein, dass Sie nur noch auf .NET Core ausgeführt werden können.

Das Metapaket `Microsoft.NETCore.App` hat das Framework `netcoreapp` als Ziel. Es bietet Zugriff auf ~60-Bibliotheken, ~40 werden durch das `NETStandard.Library`-Paket bereitgestellt, und ~20 weitere werden zusätzlich bereitgestellt. Sie können auf zusätzliche Bibliotheken verweisen, die `netcoreapp` oder kompatible Frameworks wie z.B. `netstandard` als Ziel haben, um den Zugriff auf zusätzliche APIs zu erhalten.

Die meisten der zusätzlichen Bibliotheken, die von `Microsoft.NETCore.App` bereitgestellt werden, haben ebenfalls `netstandard` als Ziel, vorausgesetzt, dass ihre Abhängigkeiten von anderen `netstandard`-Bibliotheken erfüllt werden. Dies bedeutet, dass `netstandard`-Bibliotheken auch auf diese Pakete als Abhängigkeiten verweisen können.
