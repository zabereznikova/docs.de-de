---
title: .NET Core-Versionskontrolle
description: Informationen zur Versionierung in .NET Core
author: bleroy
ms.author: mairaw
ms.date: 02/13/2018
ms.openlocfilehash: 33c545fdea254133fe6e65f4d6dd725f5184faec
ms.sourcegitcommit: 640cee8fc5d256cdd80e5b80240469feac10499e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2018
ms.locfileid: "36298239"
---
# <a name="net-core-versioning"></a>.NET Core-Versionskontrolle

.NET Core besteht aus [NuGet-Paketen](../packages.md), Tools und Frameworks, die als eine Einheit verteilt werden. Jede dieser Plattformschichten kann eine separate Versionsangabe ausweisen. Obwohl es ein gewisses Maß an Flexibilität bei der Versionskontrolle gibt, möchte man die Plattform als Einheit versionieren, damit das Produkt einfacher zu verstehen ist.

In diesem Artikel soll geklärt werden, wie das .NET Core SDK und die Runtime versioniert werden.

Es gibt viele bewegliche Teile, die in .NET Core unabhängige Versionsangaben haben können. Ab .NET Core 2.0 gibt es jedoch eine leicht verständliche Versionsnummer der höchsten Ebene, die als *die* Version von .NET Core als Ganzes angesehen wird. Im Rest dieses Dokuments wird ausführlich auf die Versionierung aller Teile eingegangen. Diese Informationen können z.B. für Sie wichtig sein, wenn Sie ein Paket-Manager sind.

> [!IMPORTANT]
> Die in diesem Thema beschriebenen Details zur Versionsverwaltung gelten nicht für die aktuelle Version von SDK und Runtime für .NET Core.
> Das Versionsschema ändert sich in künftigen Releases. Die aktuellen Vorschläge werden im Repository [dotnet/designs](https://github.com/dotnet/designs/pull/29) gezeigt.

## <a name="versioning-details"></a>Versionsinformationen

Ab .NET Core 2.0 weisen Downloads eine einzige Versionsnummer im Dateinamen auf. Folgende Versionsnummern wurden vereinheitlicht.

* das freigegebene Framework und die damit verknüpfte Runtime
* das .NET Core SDK und die verknüpfte .NET Core-CLI
* das `Microsoft.NETCore.App`-Metapaket

Der Gebrauch einer einzelnen Versionsnummer erleichtert es Benutzern zu wissen, welche Version des SDK sie auf ihren Entwicklungscomputern installieren müssen und was die entsprechende Version des freigegebenen Frameworks sein soll, wenn sie eine Produktionsumgebung bereitstellen. Beim Herunterladen eines SDK oder einer Runtime ist die angezeigt Versionsnummer die gleiche.

### <a name="installers"></a>Installer

Ab .NET Core 2.0 folgen die Downloads für die [täglichen Builds](https://github.com/dotnet/core-setup#daily-builds) und [Releases](https://www.microsoft.com/net/download/core) einem neuen Benennungsschema, das leichter verständlich ist.
Die Benutzeroberfläche des Installer bei diesen Downloads wurde angepasst, sodass sie nun die Namen und Versionen der installierten Komponenten übersichtlich anzeigen. Insbesondere weisen Titel jetzt die gleiche Versionsnummer auf, die auch im Dateinamen des Downloads verwendet wird.

#### <a name="file-name-format"></a>Dateinamenformat

`[product]-[component]-[major].[minor].[patch]-[previewN]-[optional build #]-[rid].[file ext]`

Im Folgenden finden Sie einige Beispiele für dieses Format:

```
dotnet-runtime-2.0.4-osx.10.12-x64.pkg            # Mac runtime installer
dotnet-sdk-2.0.4-win-x64.exe                      # Windows SDK installer
dotnet-sdk-2.0.4-linux-x64.tar.gz                 # Linux binary archive

#Ubuntu file set needed for the SDK
dotnet-host-2.0.4-ubuntu.16.04-x64.deb            # Host / muxer and host policy
dotnet-runtime-2.0.4-ubuntu.16.04-x64.deb         # runtime
dotnet-sdk-2.0.4-ubuntu.16.04-x64.deb             # SDK tools
```

Das Format ist lesbar und zeigt genau an, was sie herunterladen, welche Version dies ist und wo sie diese verwenden können. Der Laufzeitpaketname enthält `runtime` und das SDK `SDK`.

#### <a name="ui-string-format"></a>UI-Zeichenfolgenformat

Alle Websitebeschreibungen und UI-Zeichenfolgen im Installer sind weiterhin konsistent, genau und einfach. Die folgende Tabelle enthält einige Beispiele:

| Installer | Fenstertitel                          | Anderer Inhalt im Installer | Das wird installiert                               |
| :--       | :--                                   | :--                        | :--                                             |
| SDK       | .NET Core 2.0 SDK (x64)-Installer     | .NET Core 2.0.4 SDK        | .NET Core 2.0.4-Tools + .NET Core 2.0.4-Runtime |
| Laufzeit   | .NET Core 2.0 Runtime (x64)-Installer | .NET Core 2.0.4-Runtime    | .NET Core 2.0.4-Runtime                         |

Vorschauversionen unterscheiden sich nur geringfügig:

| Installer | Fenstertitel                                    | Anderer Inhalt im Installer        | Das wird installiert                                                   |
| :--       | :--                                             | :--                               | :--                                                                 |
| SDK       | .NET Core 2.0 Preview 1 SDK (x64)-Installer     | .NET Core 2.0.0 Preview 1 SDK     | .NET Core 2.0.0 Preview 1-Tools + .NET Core 2.0.0 Preview 1-Runtime |
| Laufzeit   | .NET Core 2.0 Preview 1 Runtime (x64)-Installer | .NET Core 2.0.0 Preview 1-Runtime | .NET Core 2.0.0 Preview 1-Runtime                                   |

Möglicherweise enthält eine SDK Version mehr als eine Version der Runtime. Wenn dies der Fall ist, sieht die UI des Installer folgendermaßen aus (es wird nur die SDK Version gezeigt, die installierten Runtimeversionen werden auf einer Zusammenfassungsseite am Ende des Installationsprozesse unter Windows und Mac angezeigt):

| Installer | Fenstertitel                      | Anderer Inhalt im Installer                                   | Das wird installiert                                                         |
| :--       | :--                               | :--                                                          | :--                                                                       |
| SDK       | .NET Core 2.1 SDK (x64)-Installer | .NET Core 2.1.1 SDK <br> .NET Core 2.1.1-Runtime <br> .NET Core 2.0.6-Runtime | .NET Core 2.1.1-Tools + .NET Core 2.1.1-Runtime + .NET Core 2.0.6-Runtime |

Möglicherweise müssen auch nur die .NET Core-Tools aktualisiert werden, ohne dass Änderungen der Runtime nötig sind. In diesem Fall wird die SDK Version erhöht (z.B. auf 2.1.2), und die Runtime schließt auf, wenn sie das nächste Mal ausgeliefert wird (z.B. werden die Runtime und das SDK das nächste Mal in Version 2.1.3 geliefert).

### <a name="package-managers"></a>Paket-Manager

.NET Core kann neben Microsoft auch von anderen Entitäten verteilt werden. Insbesondere Besitzer einer Linux-Verteilung und Paketverwalter verwenden möglicherweise .NET Core-Pakete in ihren Paket-Managern. Empfehlungen zur Benennung und Versionierung dieser Pakete finden Sie unter [.NET Core distribution packaging (Packen von .NET Core-Verteilungen)](../build/distribution-packaging.md).

#### <a name="minimum-package-set"></a>Minimales Paketset

* `dotnet-runtime-[major].[minor]`: eine Runtime mit der angegebenen Version (nur die neueste Patchversion für eine bestimmte Kombination aus Haupt- und Nebenversionen sollte im Paket-Manager verfügbar sein). Neue Patchversionen aktualisieren das Paket, aber neue Haupt- oder Nebenversionen sind getrennte Pakete.

  **Abhängigkeiten**: `dotnet-host`

* `dotnet-sdk`: das neueste SDK `update` führt ein Rollforward für Haupt-, Neben- und Patchversionen aus.

  **Abhängigkeiten**: die neueste `dotnet-sdk-[major].[minor]`

* `dotnet-sdk-[major].[minor]`: das SDK mit der angegebenen Version. Die angegebene Version ist die höchste enthaltene Version von enthaltenen freigegebenen Frameworks, sodass Benutzer problemlos ein SDK mit einem freigegebenen Framework verknüpfen können. Neue Patchversionen aktualisieren das Paket, aber neue Haupt- oder Nebenversionen sind getrennte Pakete.

  **Abhängigkeiten**: `dotnet-host`, ein oder mehrere `dotnet-runtime-[major].[minor]` (eine dieser Runtimes wird durch den SDK Code selbst verwendet, mit den anderen können Benutzer erstellen und ausführen).

* `dotnet-host`: der neueste Host.

##### <a name="preview-versions"></a>Vorschauversionen

Paketverwalter können möglicherweise Vorschauversionen der Runtime und SDKs einschließen. Beziehen Sie diese Vorschauversionen niemals in das nicht versionierte `dotnet-sdk`-Paket ein. Sie können sie aber als Pakete mit Versionsnummer mit einem zusätzlichen Vorschaumarker freigegeben, der an die Abschnitte der Haupt- und Nebenversion des Namens angefügt ist. Beispielsweise gibt es möglicherweise ein Paket `dotnet-sdk-2.0-preview1-final`.

### <a name="docker"></a>Docker

Eine allgemeine Namenskonvention für ein Dockertag ist das Platzieren der Versionsnummer vor den Komponentennamen. Diese Konvention wird möglicherweise weiter eingesetzt. Die aktuellen Tags enthalten nur die Version der Runtime in folgender Form:

* 1.0.8-runtime
* 1.0.8-sdk
* 2.0.4-runtime
* 2.0.4-sdk
* 2.1.1-runtime
* 2.1.1-sdk

Die SDK Tags sollten aktualisiert werden, sodass sie die Version des SDK statt der Runtime widerspiegeln.

Es besteht die Möglichkeit, dass die .NET Core-Tools (einschließlich SDK) repariert, aber mit einer vorhandenen Runtime erneut bereitgestellt werden. In diesem Fall wird die SDK-Version erhöht (z.B. auf 2.1.2), und die Runtime schließt auf, wenn sie das nächste Mal ausgeliefert wird (z.B. werden die Runtime und das SDK das nächste Mal in Version 2.1.3 geliefert).

## <a name="semantic-versioning"></a>Semantische Versionskontrolle

.NET Core verwendet die [semantische Versionskontrolle (SemVer)](http://semver.org/) und übernimmt den Gebrauch der `MAJOR.MINOR.PATCH`-Versionierung mithilfe der verschiedenen Teile der Versionsnummer, um den Grad und die Typ der Änderung zu beschreiben.

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

Die optionalen Teile `PRERELEASE` und `BUILDNUMBER` sind nie Bestandteil von unterstützten Versionen und sind nur in nächtlichen Builds vorhanden, die lokal aus Quellzielen und nicht unterstützten Vorschauversionen erstellt werden.

### <a name="how-version-numbers-are-incremented"></a>Wie werden Versionsnummern inkrementiert?

`MAJOR` wird inkrementiert, wenn:

- eine älter Version nicht mehr unterstützt wird
- eine neue `MAJOR`-Version einer vorhandenen Abhängigkeit übernommen wird
- die Standardeinstellung eines Kompatibilitätsproblems deaktiviert wird

`MINOR` wird inkrementiert, wenn:

- eine öffentliche API-Oberfläche hinzugefügt wird
- ein neues Verhalten hinzugefügt wird
- eine neue `MINOR`-Version einer vorhandenen Abhängigkeit übernommen wird
- eine neue Abhängigkeit eingeführt wird

`PATCH` wird inkrementiert, wenn:

- Fehlerkorrekturen vorgenommen werden
- Unterstützung für eine neuere Plattform hinzugefügt wird
- eine neue `PATCH`-Version einer vorhandenen Abhängigkeit übernommen wird
- eine andere Änderung vorgenommen wurde, die keinem der zuvor beschriebenen Fälle entspricht

Wenn mehrere Änderungen vorgenommen wurden, wird das höchste Element, was von den einzelnen Änderungen betroffen ist, inkrementierte, und die folgenden werden auf 0 (null) zurückgesetzt. Wenn z.B. `MAJOR` inkrementiert wird, werden `MINOR` und `PATCH` auf 0 (null) zurückgesetzt. Wenn `MINOR` inkrementiert wird, wird `PATCH` auf 0 (null) zurückgesetzt, während `MAJOR` nicht beeinträchtigt wird.

### <a name="preview-versions"></a>Vorschauversionen

Der Version von Vorschauversionen ist ein `-preview[number]-([build]|"final")` angehängt. Beispielsweise `2.0.0-preview1-final`.

### <a name="servicing-versions"></a>Wartung von Versionen

Nach Erscheinen eines Release produzieren die Releaseabteilungen im Allgemeinen keine täglichen Builds mehr und beginnen stattdessen mit der Produktion von Wartungsbuilds. Der Versionsangabe von Wartungsversionen ist ein `-servicing-[number]` angehängt. Beispielsweise `2.0.1-servicing-006924`.

### <a name="lts-vs-current"></a>LTS vs. aktuell

Es gibt zwei verschiedene Versionsreihen für .NET Core: Long Term Support und Aktuell So können sich Benutzer für den Stabilitätsgrad und neue Funktionen entscheiden, die sie möchten, ohne das der Support verloren geht.

- LTS bedeutet, dass Sie weniger häufig neue Funktionen bekommen, gleichzeitig aber eine voller entwickelte Plattform haben. LTS verfügt zudem über einen längeren Supportzeitraum.
- Aktuell bedeutet, dass Sie häufiger neue Funktionen und APIs erhalten. Dabei ist allerdings der Nachteil, dass Sie Updates in einem engeren Zeitfenster installieren müssen und diese mit einer höheren Frequenz bereitgestellt werden. Aktuell verfügt auch über vollen Support. Der Supportzeitraum ist allerdings kürzer als bei LTS.

Eine „aktuelle“ Version kann auf LTS höher gestuft werden.

LTS und Aktuell sollten als Bezeichnungen angesehen werden, die wir bestimmten Versionen geben, um deren Grad an Support deutlich zu machen.

Weitere Informationen finden Sie unter [.NET Core Support Lifecycle Fact Sheet (Fakten zur Lebensdauer des .NET Core Support)](https://www.microsoft.com/net/core/support).

## <a name="versioning-scheme-details"></a>Informationen zum Versionsschema

.NET Core besteht aus den folgenden Teilen:

- Ein Host: entweder *dotnet.exe* für vom Framework abhängige Anwendungen oder *\<appname>.exe* für eigenständige Anwendungen.
- einem SDK (die Tools, die ein Entwickler auf seinem Computer benötigt, aber nicht während der Produktion)
- eine Runtime
- eine freigegebene Frameworkimplementierung, die in Paketen verteilt wird Jedes Paket wird unabhängig versioniert, dies gilt besonders für die Patchversionierung.
- ein Satz von [Metapaketen](../packages.md), die auf detaillierte Pakete als versionierte Einheit verweisen (optional) Metapakete können separat von Paketen versioniert werden.

.NET Core enthält zudem einen Satz von Zielframeworks (z.B. `netstandard` oder`netcoreapp`), die mit der Inkrementierung von Versionsnummern einen immer größeren API-Satz darstellen.

### <a name="net-standard"></a>.NET-Standard

.NET Standard hat ein `MAJOR.MINOR`-Versionierungsschema verwendet. Die `PATCH`-Ebene ist für .NET Standard nicht nützlich, da sie einen Satz von Verträgen ausdrückt, die seltener durchlaufen werden. Sie stellt nicht die gleichen Anforderungen für die Versionierung wie eine tatsächliche Implementierung dar.

Es gibt keine echte Kopplung zwischen Versionen von .NET Standard und .NET Core: .NET Core 2.0 implementiert .NET Standard 2.0, aber es gibt keine Garantie, dass zukünftige Versionen von .NET Core die gleiche Version von .NET Standard zuordnen. .NET Core kann APIs ausliefern, die nicht von .NET Standard definiert sind und kann so neue Versionen ausliefern, ohne das ein neues .NET Standard erforderlich ist. .NET Standard ist zudem ein Konzept, das für andere Ziele gilt, wie z.B. .NET Framework oder Mono, auch wenn dessen Beginn zufällig mit dem von .NET Core zusammenfällt.

### <a name="packages"></a>Pakete

Bibliothekspakete verbessern sich unabhängig und verfügen über eine unabhängige Versionsangabe. Pakete, die sich mit .NET Framework System.\*-Assemblys überschneiden, verwenden normalerweise 4.x-Versionen, die mit der 4.x-Versionskontrolle von .NET Framework ausgerichtet werden. Pakete, die sich nicht mit den .NET Framework-Bibliotheken überschneiden (z.B. [`System.Reflection.Metadata`](https://www.nuget.org/packages/System.Reflection.Metadata)) beginnen normalerweise bei 1.0 und erhöhen ab dort.

Die Pakete, die von [`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library) beschrieben sind, werden besonders behandelt, da sie sich an der Basis der Plattform befinden.

`NETStandard.Library`-Pakete werden in der Regel als Gruppe versioniert, da sie untereinander über Abhängigkeiten auf Implementierungsebene verfügen.

### <a name="metapackages"></a>Metapakete

Die Versionierung für .NET Core-Metapakete basiert auf der Version von .NET Core, zu der sie gehören.

Die Metapakete in .NET Core 2.1.3 sollten z.B. alle 2.1 als ihre `MAJOR`- und `MINOR`-Versionsnummer haben.

Die Patchversion für die Metapakete wird jedes Mal inkrementiert, wenn ein verwiesenes Paket aktualisiert wird. Patchversionen erhalten keine aktualisierte Frameworkversion. Die Metapakete sind deshalb nicht mit SemVer kompatibel, weil ihr Schema der Versionskontrolle nicht den Grad der Änderung in den zugrundeliegenden Paketen darstellt, sondern hauptsächlich die API-Ebene.

Es existieren aktuell zwei primäre Metapakete für .NET Core:

**Microsoft.NETCore.App**

- v1.0 ab .NET Core 1.0 (diese Versionen stimmen überein)
- Ist dem `netcoreapp`-Framework zugeordnet
- Beschreibt die Pakete in der .NET Core-Verteilung

Hinweis: [`Microsoft.NETCore.Portable.Compatibility`](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility) ist ein weiteres .NET Core-Metapaket, das existiert, um die Kompatibilität mit .NET-Implementierungen zu gewährleisten, die vor .NET Standard vorgenommen wurden. Es wird keinem bestimmten Framework zugeordnet und wird daher wie ein Paket versioniert.

**NETStandard.Library**

[`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library) beschreibt die Bibliotheken, die Teil von [.NET Standard](../../standard/library.md) sind. Gilt für alle .NET-Implementierungen (z.B. .NET Framework, .NET Core und Mono), die .NET-Standard unterstützen.

### <a name="target-frameworks"></a>Zielframeworks

Zielframework-Versionen werden aktualisiert, wenn neue APIs hinzugefügt werden. Sie verfügen über kein Konzept der Patchversion, da sie die API-Form und keine Implementierungsprobleme darstellen. Major- und Minor-Versionierung folgt SemVer-Regeln, die bereits angegeben wurden, und stimmt mit den `MAJOR`- und `MINOR`-Nummern der Verteilung von .NET Framework überein, die sie implementieren.

## <a name="versioning-in-practice"></a>Versionierung in der Praxis

Wenn Sie .NET Core herunterladen, enthält der Name der heruntergeladenen Datei die Version, z.B. `dotnet-sdk-2.0.4-win10-x64.exe`.

Es gibt täglich Commits und Pull Requests auf .NET Core-Repositorys auf GitHub, wodurch viele Bibliotheken neue Builds erhalten. Es ist nicht sehr praktisch, neue öffentliche .NET Core-Versionen für jede Änderung zu erstellen. Stattdessen werden die Änderungen über einen unbestimmten Zeitraum (z.B. Wochen oder Monate) aggregiert, bevor eine neue, öffentliche stabile .NET Core-Version erstellt wird.

Eine neue Version von .NET Core bringt Folgendes mit sich:

- Neue Versionen von Paketen und Metapaketen
- Neue Versionen von verschiedenen Frameworks, vorausgesetzt, neue APIs werden hinzugefügt
- Neue Version der .NET Core-Verteilung

### <a name="shipping-a-patch-release"></a>Versand einer Patchversion

Nach der Auslieferung einer Hauptversion von .NET Core (z.B. V 2.0.0) werden keine Änderungen auf Patchebene an .NET Core-Bibliotheken zur Behebung von Fehlern und zur Verbesserung der Leistung sowie der Zuverlässigkeit vorgenommen. Dies bedeutet, dass keine neuen APIs eingeführt werden. Die verschiedenen Metapakete werden aktualisiert, um auf die aktualisierten .NET Core-Bibliothekspakete zu verweisen. Die Metapakete werden als Patchupdates versioniert (`MAJOR.MINOR.PATCH`). Zielframeworks werden niemals als Teil einer Patchversion aktualisiert. Eine neue .NET Core-Verteilung wird mit einer Versionsnummer freigegeben, die mit der des `Microsoft.NETCore.App`-Metadatenpakets übereinstimmt.

### <a name="shipping-a-minor-release"></a>Versenden einer Nebenversion

Nach der Auslieferung einer NET Core-Version mit einer inkrementierten `MAJOR`-Versionsnummer werden neue APIs den .NET Core-Bibliotheken hinzugefügt, sodass neue Szenarios ermöglicht werden. Die verschiedenen Metapakete werden aktualisiert, um auf die aktualisierten .NET Core-Bibliothekspakete zu verweisen. Die Metapakete werden als Patchupdates mit `MAJOR`- und `MINOR`-Versionsnummern versioniert, die mit der neuen Frameworkversion übereinstimmen. Namen neuer Zielframeworks mit neuen `MAJOR.MINOR`-Versionen werden hinzugefügt, um die neuen APIs zu beschreiben (z.B. `netcoreapp2.1`). Eine neue .NET Core-Verteilung wird mit einer übereinstimmenden Versionsnummer für das Metapaket `Microsoft.NETCore.App` freigegeben.

### <a name="shipping-a-major-release"></a>Versenden einer Hauptversion

Jedes Mal wenn eine neue Hauptversion von .NET Core ausgeliefert wird, wird die `MAJOR`-Versionsnummer inkrementiert, und die `MINOR`-Versionsnummer wird auf 0 (null) zurückgesetzt. Die neue Hauptversion enthält mindestens alle APIs, die durch Nebenversionen nach der vorherigen Hauptversion hinzugefügt wurden. Eine neue Hauptversion sollte neue, relevante Szenarios ermöglichen und den Support für eine ältere Plattform überflüssig machen.

Die verschiedenen Metapakete werden aktualisiert, um auf die aktualisierten .NET Core-Bibliothekspakete zu verweisen. Das [`Microsoft.NETCore.App`](https://www.nuget.org/packages/Microsoft.NETCore.App)-Metapakete und das `netcore`-Zielframework werden als Hauptupdates versioniert, die mit der `MAJOR`-Versionsnummer der neuen Version übereinstimmen.

## <a name="see-also"></a>Siehe auch

[Zielframeworks](../../standard/frameworks.md)  
[.NET Core distribution packaging (Verpacken der Verteilung in .NET Core)](../build/distribution-packaging.md)  
[.NET Core Support Lifecycle Fact Sheet](https://www.microsoft.com/net/core/support)  
[.NET Core 2+ Versionsbindung](https://github.com/dotnet/designs/issues/3)  
