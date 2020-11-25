---
title: Versionsverwaltung für .NET Core-Runtime und SDK
description: In diesem Artikel erfahren Sie, wie das .NET Core SDK und die Runtime versioniert werden (ähnlich der semantischen Versionierung).
ms.date: 06/24/2020
ms.openlocfilehash: baa3f94947699d21ce7426054359d91f7781b565
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726703"
---
# <a name="overview-of-how-net-core-is-versioned"></a>Übersicht über die .NET Core-Versionsverwaltung

.NET Core bezieht sich auf die .NET Core Runtime und das .NET Core SDK, das die Tools enthält, die Sie für die Entwicklung von Anwendungen benötigen. .NET Core SDKs sind so konzipiert, dass sie mit jeder früheren Version der .NET Core Runtime funktionieren. Dieser Artikel beschreibt die Runtime und die SDK-Versionsstrategie. Eine Erläuterung der Versionsnummern für .NET Standard finden Sie in dem Artikel, der [.NET Standard](../../standard/net-standard.md#net-implementation-support) vorstellt.

Die .NET Core Runtime und das .NET Core SDK fügen neue Features mit unterschiedlicher Geschwindigkeit hinzu: Im Allgemeinen bietet das .NET Core SDK aktualisierte Tools schneller als .NET Core Runtime die Runtime ändert, die Sie in der Produktion verwenden.

## <a name="versioning-details"></a>Versionsinformationen

„.NET Core 2.1“ bezieht sich auf die .NET Core Runtime-Versionsnummer. Die .NET Core Runtime verfolgt einen Hauptversions-/Nebenversions-/Patchansatz für die Versionsverwaltung, der [semantische Versionierung](#semantic-versioning) verwendet.

Das .NET Core SDK folgt keiner semantischen Versionierung. Das .NET Core SDK wird schneller veröffentlicht, und seine Versionen müssen sowohl die angepasste Runtime als auch die eigenen Nebenversions- und Patchreleases des SDK kommunizieren. Die ersten beiden Stellen der .NET Core SDK-Version sind für die .NET Core Runtime reserviert, mit der sie veröffentlicht wurde. Jede Version des SDK kann Anwendungen für diese Runtime bzw. niedrigere Versionen erstellen.

Die dritte Stelle der SDK-Versionsnummer gibt sowohl die Nebenversions- als auch die Patchnummer an. Die Nebenversion wird mit 100 multipliziert. Nebenversion 1, Patchversion 2 würde als 102 dargestellt. Die letzten zwei Ziffern stehen für die Patchnummer. Das Release von .NET Core 2.2 kann z.B. Releases wie in der folgenden Tabelle gezeigt erstellen:

| Änderung                | .NET Core Runtime | .NET Core SDK (\*) |
|-----------------------|-------------------|-------------------|
| Erstrelease       | 2.2.0             | 2.2.100           |
| SDK-Patch             | 2.2.0             | 2.2.101           |
| Runtime und SDK-Patch | 2.2.1             | 2.2.102           |
| SDK-Featureänderung    | 2.2.1             | 2.2.200           |

(\*) In diesem Diagramm wird die .NET Core-Runtime 2.2 als Beispiel verwendet, da 2.1.300 als erstes SDK für .NET Core 2.1 festgelegt wurde. Weitere Informationen finden Sie unter [.NET Core version selection (.NET Core-Versionsauswahl)](selection.md).

HINWEISE:

- Wenn das SDK vor einem Runtimefeatureupdate 10 Featureupdates aufweist, werden die Versionsnummern in die 1000er-Serie mit Nummern wie 2.2.1000 als Featurerelease nach 2.2.900 übernommen. Diese Situation wird nicht erwartet.
- 99 Patchreleases ohne Featurerelease treten nicht auf. Nähert sich ein Release dieser Version, wird ein Featurerelease erzwungen.

Weitere Details finden Sie im ursprünglichen Vorschlag im Repository [dotnet/designs](https://github.com/dotnet/designs/pull/29).

## <a name="semantic-versioning"></a>Semantische Versionierung

Die .NET Core *Runtime* verwendet im Großen und Ganzen die [semantische Versionierung (SemVer)](https://semver.org/) und übernimmt die Verwendung der `MAJOR.MINOR.PATCH`-Versionierung mithilfe der verschiedenen Teile der Versionsnummer, um den Grad und den Typ der Änderung zu beschreiben.

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

Die optionalen Teile `PRERELEASE` und `BUILDNUMBER` sind nie Bestandteil von unterstützten Versionen und sind nur in nächtlichen Builds vorhanden, die lokal aus Quellzielen und nicht unterstützten Vorschauversionen erstellt werden.

### <a name="understand-runtime-version-number-changes"></a>Verstehen von Änderungen der Runtimeversionsnummer

`MAJOR` wird inkrementiert, wenn:

- Signifikante Änderungen im Produkt oder eine neue Produktausrichtung auftreten.
- Aktuelle Änderungen vorgenommen wurden. Die Messlatte zum Akzeptieren von aktuellen Änderungen hoch liegt.
- eine älter Version nicht mehr unterstützt wird
- eine neue `MAJOR`-Version einer vorhandenen Abhängigkeit übernommen wird

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

## <a name="version-numbers-in-file-names"></a>Versionsnummern in Dateinamen

Die für .NET Core heruntergeladenen Dateien tragen die Versionsnummer, zum Beispiel `dotnet-sdk-2.1.300-win10-x64.exe`.

### <a name="preview-versions"></a>Vorschauversionen

Der Version von Vorschauversionen ist ein `-preview[number]-([build]|"final")` angehängt. Beispielsweise `2.0.0-preview1-final`.

### <a name="servicing-versions"></a>Wartung von Versionen

Nach Erscheinen eines Release produzieren die Releaseabteilungen im Allgemeinen keine täglichen Builds mehr und beginnen stattdessen mit der Produktion von Wartungsbuilds. Der Versionsangabe von Wartungsversionen ist ein `-servicing-[number]` angehängt. Beispielsweise `2.0.1-servicing-006924`.

## <a name="relationship-to-net-standard-versions"></a>Beziehung zu .NET Standard-Versionen

.NET Standard besteht aus einer .NET-Referenzassembly. Es gibt mehrere plattformspezifische Implementierungen. Die Referenzassembly enthält die Definition von .NET-APIs, die Teil einer angegebenen .NET Standard-Version sind. Jede Implementierung erfüllt den .NET Standard-Vertrag für die jeweilige Plattform. Sie können mehr über .NET Standard im Artikel zu [.NET Standard](../../standard/net-standard.md) im .NET-Leitfaden erfahren.

Die .NET Standard-Referenzassembly verwendet ein `MAJOR.MINOR`-Schema für die Versionsverwaltung. Die `PATCH`-Ebene ist für .NET Standard nicht sinnvoll, da sie nur eine API-Spezifikation bereitstellt (keine Implementierung) und per Definition jede Änderung an der API eine Änderung im Funktionsumfang und damit eine neue `MINOR`-Version darstellen würde.

Die Implementierungen auf jeder Plattform können aktualisiert werden (in der Regel als Teil des Plattformreleases) und sind daher für die Programmierer, die den .NET Standard auf dieser Plattform verwenden, nicht ersichtlich.

Jede Version von .NET Core implementiert eine Version von .NET Standard. Das Implementieren einer Version von .NET Standard bedeutet Unterstützung für frühere Versionen von .NET Standard. .NET Standard -und .NET Core-Version unabhängig voneinander. Es ist Zufall, dass .NET Core 2.0 .NET Standard 2.0 implementiert. .NET Core 2.1 implementiert auch .NET Standard 2.0. .NET Core unterstützt zukünftige Versionen von .NET Standard, sobald diese verfügbar werden.

| .NET Core | .NET-Standard |
|-----------|---------------|
| 1.0       | bis zu 1.6     |
| 2.0       | bis zu 2.0     |
| 2.1       | bis zu 2.0     |
| 2.2       | bis zu 2.0     |
| 3.0       | bis zu 2.1     |
| 3.1       | bis zu 2.1     |

Eine interaktive Tabelle der .NET Standard-Versionen und deren Entsprechung mit .NET-Implementierungen finden Sie unter [.NET Standard-Versionen](https://dotnet.microsoft.com/platform/dotnet-standard#versions).

## <a name="see-also"></a>Siehe auch

- [Zielframeworks](../../standard/frameworks.md)
- [.NET Core distribution packaging (Verpacken der Verteilung in .NET Core)](../distribution-packaging.md)
- [.NET Core Support Lifecycle Fact Sheet](https://dotnet.microsoft.com/platform/support/policy)
- [.NET Core 2+ Versionsbindung](https://github.com/dotnet/designs/issues/3)
- [Docker-Images für .NET Core](https://hub.docker.com/_/microsoft-dotnet/)
