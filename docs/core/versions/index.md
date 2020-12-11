---
title: Versionsverwaltung für die .NET-Runtime und das .NET SDK
description: In diesem Artikel erfahren Sie, wie das .NET SDK und die Runtime versioniert werden (ähnlich der semantischen Versionierung).
ms.date: 12/07/2020
ms.openlocfilehash: 2fe0b162b52f1e4500ec87f7d5d92054cd569552
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009305"
---
# <a name="overview-of-how-net-is-versioned"></a>Übersicht über die .NET-Versionsverwaltung

Mit der [.NET-Runtime und dem .NET SDK](../introduction.md#sdk-and-runtimes) werden neue Features zu unterschiedlichen Frequenzen hinzugefügt. In der Regel wird das SDK häufiger aktualisiert als die Runtime. Dieser Artikel beschreibt die Runtime und die SDK-Versionsnummern.

## <a name="versioning-details"></a>Versionsinformationen

Die .NET-Runtime verfolgt einen Hauptversions-/Nebenversions-/Patchansatz für die Versionsverwaltung, der [semantische Versionierung](#semantic-versioning) verwendet.

Das .NET SDK folgt keiner semantischen Versionierung. Das .NET SDK wird schneller veröffentlicht, und seine Versionsnummern müssen sowohl die angepasste Runtime als auch die eigenen Nebenversions- und Patchreleases des SDK kommunizieren.

Die ersten beiden Stellen der .NET SDK-Versionsnummern sind für die .NET Runtime reserviert, mit der sie veröffentlicht wurde. Jede Version des SDK kann Anwendungen für diese Runtime bzw. niedrigere Versionen erstellen.

Die dritte Stelle der SDK-Versionsnummer gibt sowohl die Nebenversions- als auch die Patchnummer an. Die Nebenversion wird mit 100 multipliziert. Nebenversion 1, Patchversion 2 würde als 102 dargestellt. Die letzten zwei Ziffern stehen für die Patchnummer. Im Folgenden ist eine mögliche Sequenz der Runtime- und SDK-Versionsnummern aufgeführt:

| Change                | .Net-Runtime      | .NET SDK (\*)     |
|-----------------------|-------------------|-------------------|
| Erstrelease       | 2.2.0             | 2.2.100           |
| SDK-Patch             | 2.2.0             | 2.2.101           |
| Runtime und SDK-Patch | 2.2.1             | 2.2.102           |
| SDK-Featureänderung    | 2.2.1             | 2.2.200           |

HINWEISE:

- Wenn das SDK vor einem Runtimefeatureupdate 10 Featureupdates aufweist, werden die Versionsnummern in die 1000er-Serie mit Nummern wie 2.2.1000 als Featurerelease nach 2.2.900 übernommen. Diese Situation wird nicht erwartet.
- 99 Patchreleases ohne Featurerelease treten nicht auf. Nähert sich ein Release dieser Version, wird ein Featurerelease erzwungen.

Weitere Details finden Sie im ursprünglichen Vorschlag im Repository [dotnet/designs](https://github.com/dotnet/designs/pull/29).

## <a name="semantic-versioning"></a>Semantische Versionierung

Die .NET-*Runtime* verwendet im Großen und Ganzen die [semantische Versionierung (SemVer)](https://semver.org/) und übernimmt die Verwendung der `MAJOR.MINOR.PATCH`-Versionierung mithilfe der verschiedenen Teile der Versionsnummer, um den Grad und den Typ der Änderung zu beschreiben.

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

Die für .NET heruntergeladenen Dateien tragen die Versionsnummer, zum Beispiel `dotnet-sdk-2.1.300-win10-x64.exe`.

### <a name="preview-versions"></a>Vorschauversionen

Der Versionsnummer von Vorschauversionen ist ein `-preview[number]-([build]|"final")` angehängt. Beispielsweise `2.0.0-preview1-final`.

### <a name="servicing-versions"></a>Wartung von Versionen

Nach Erscheinen eines Release produzieren die Releaseabteilungen im Allgemeinen keine täglichen Builds mehr und beginnen stattdessen mit der Produktion von Wartungsbuilds. Der Versionsangabe von Wartungsversionen ist ein `-servicing-[number]` angehängt. Beispielsweise `2.0.1-servicing-006924`.

## <a name="relationship-to-net-standard-versions"></a>Beziehung zu .NET Standard-Versionen

.NET Standard besteht aus einer .NET-Referenzassembly. Es gibt mehrere plattformspezifische Implementierungen. Die Referenzassembly enthält die Definition von .NET-APIs, die Teil einer angegebenen .NET Standard-Version sind. Jede Implementierung erfüllt den .NET Standard-Vertrag für die jeweilige Plattform.

Die .NET Standard-Referenzassembly verwendet ein `MAJOR.MINOR`-Schema für die Versionsverwaltung. Die `PATCH`-Ebene ist für .NET Standard nicht sinnvoll, da sie nur eine API-Spezifikation bereitstellt (keine Implementierung) und per Definition jede Änderung an der API eine Änderung im Funktionsumfang und damit eine neue `MINOR`-Version darstellen würde.

Die Implementierungen auf jeder Plattform können aktualisiert werden (in der Regel als Teil des Plattformreleases) und sind daher für die Programmierer, die den .NET Standard auf dieser Plattform verwenden, nicht ersichtlich.

Weitere Informationen finden Sie unter [.NET Standard](../../standard/net-standard.md).

## <a name="see-also"></a>Siehe auch

- [Zielframeworks](../../standard/frameworks.md)
- [Packen einer Verteilung von .NET](../distribution-packaging.md)
- [Fakten zur Lebensdauer der .NET-Unterstützung](https://dotnet.microsoft.com/platform/support/policy)
- [Docker-Images für .NET](https://hub.docker.com/_/microsoft-dotnet/)
