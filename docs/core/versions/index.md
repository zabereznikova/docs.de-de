---
title: .NET Core-Versionskontrolle | Microsoft-Dokumentation
description: .NET Core-Versionskontrolle
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: f6f684b1-1d2c-4105-8376-7c1959e23803
ms.translationtype: Human Translation
ms.sourcegitcommit: 4437ce5d344cf06d30e31911def6287999fc6ffc
ms.openlocfilehash: 3cdd3ff040bfd9d307f0d0c0a07fbd0d972cbd3e
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---

# <a name="net-core-versioning"></a>.NET Core-Versionskontrolle

.NET Core ist eine Plattform von [NuGet-Paketen](../packages.md) und Frameworks und ist als Einheit aufgeteilt. Jede dieser Plattformebenen kann separat für die Produktflexibilität versioniert werden, und um die Produktveränderungen genau zu beschreiben. Obwohl es ein gewisses Maß an Flexibilität bei der Versionskontrolle gibt, möchte man die Plattform als Einheit versionieren, damit das Produkt einfacher zu verstehen ist.

Das Produkt ist in mancher Hinsicht eindeutig und wird durch einen Paket-Manager (NuGet) als Pakete beschrieben und geliefert. Während Sie in der Regel .NET Core als eigenständiges SDK laden, ist das SDK größtenteils bequemer als NuGet-Pakete zu handhaben und deshalb nicht von Paketen getrennt. Daher wird die Versionskontrolle in erster Linie für Pakete definiert und andere Mittel der Versionskontrolle folgen.

## <a name="semantic-versioning"></a>Semantische Versionskontrolle

.NET Core verwendet die [semantische Versionskontrolle (Semantic Versioning unter SemVer)](http://semver.org/) und übernimmt den Gebrauch der Versionskontrolle „major.minor.patch“ mithilfe der verschiedenen Teile der Versionsnummer, um den Grad und die Art der Änderung zu beschreiben.

Die folgende Vorlage für die Versionskontrolle wird allgemein auf .NET Core angewendet. Es gibt Fälle, bei denen die Vorlage angepasst wurde, damit sie der vorhandenen Versionskontrolle entspricht. Diese Fälle werden weiter unten in diesem Dokument beschrieben. Beispielsweise sind Frameworks nur dafür vorgesehen, Plattform- und API-Funktionen darzustellen, was jeweils der Major- bzw. Minor-Buildversion entspricht.

### <a name="versioning-form"></a>Formular der Versionskontrolle

MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]

### <a name="decision-tree"></a>Entscheidungsstruktur

MAJOR wenn:
  - Unterstützung für eine Plattform verworfen wird
  - eine neue MAJOR-Version einer vorhandenen Abhängigkeit übernommen wird 
  - Kompatibilitätsprobleme mit der Voreinstellung AUS verboten werden

MINOR wenn:
  - eine öffentliche API-Oberfläche hinzugefügt wird 
  - neues Verhalten hinzugefügt wird
  - eine neue MINOR-Version einer vorhandenen Abhängigkeit übernommen wird
  - eine neue Abhängigkeit eingeführt wird 
  
PATCH wenn:
  - Fehlerkorrekturen gemacht werden
  - Unterstützung für eine neuere Plattform hinzugefügt wird
  - eine neue PATCH-Version einer vorhandenen Abhängigkeit übernommen wird
  - jede andere Änderung (nicht anderweitig aufgezeichnet)

Wenn Sie bestimmen, was Sie im Falle mehrerer Änderungen erhöhen, wählen Sie die höchste Art der Änderung aus.

## <a name="versioning-scheme"></a>Versionsschema

.NET Core kann wie folgt definiert und versioniert werden:

- Eine Laufzeit- und Frameworkimplementierung, die als Pakete verteilt werden. Jedes Paket wird unabhängig versioniert, dies gilt besonders für die Patchversionierung.
- Ein Satz von Metapaketen, die auf detaillierte Pakete als versionierte Einheit verweisen. Metapakete werden separat von Paketen versioniert.
- Eine Reihe von Frameworks (z.B. `netstandard`), die einen zunehmend größer werdenden Satz von APIs darstellen, werden in einer Reihe Momentaufnahmen mit Versionsangabe beschrieben.

### <a name="packages"></a>Pakete

Bibliothekspakete verbessern sich unabhängig und verfügen über eine unabhängige Versionsangabe. Pakete, bei denen eine Überlappung mit .NET Framework System.\* -Assemblys besteht, verwenden normalerweise 4.x-Versionen, die mit der 4.x-Versionskontrolle von .NET Framework ausgerichtet werden. Pakete, die sich nicht mit den .NET Framework-Bibliotheken überschneiden (z.B. [System.Reflection.Metadata](https://www.nuget.org/packages/System.Reflection.Metadata)) beginnen normalerweise bei 1.0 und erhöhen ab dort.

Die Pakete, die von [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) beschrieben sind, werden besonders behandelt, da sie sich an der Basis der Plattform befinden.

- NETStandard.Library-Pakete werden in der Regel als Gruppe versioniert, da sie untereinander über Abhängigkeiten auf Implementierungsebene verfügen.
- APIs werden nur zu NETStandard.Library-Paketen als Teil der Major- und Minor-Versionen von .NET Core hinzugefügt, da dadurch eine neue `netstandard`-Version hinzugefügt werden muss. Dies erfolgt zusätzlich zu SemVer-Anforderungen.

### <a name="metapackages"></a>Metapakete

Die Versionskontrolle für .NET Core-Metapakete basiert auf dem Framework, dem sie zugeordnet sind. Die Metapakete übernehmen die höchste Versionsnummer des Frameworks (z.B. netstandard1.6), auf das sie sich in dessen Paketabschluss beziehen. 

Die Patchversion für das Metapaket wird verwendet, um Updates für das Metapaket darzustellen, um auf aktualisierte Pakete zu verweisen. Patchversionen erhalten niemals eine aktualisierte Framework-Version. Die Metapakete sind deshalb nicht mit SemVer kompatibel, da deren Schema der Versionskontrolle nicht den Grad der Änderung in den zugrundeliegenden Paketen darstellt, hauptsächlich jedoch die API-Ebene. 

Es existieren zwei primäre Metapakete für .NET Core.

**NETStandard.Library**

- v1.6 ab .NET Core 1.0 (diese Versionen stimmen in der Regel oder absichtlich nicht überein).
- Ist dem `netstandard`-Framework zugeordnet 
- Beschreibt die Pakete, die für die moderne App-Entwicklung als erforderlich gelten und dass .NET-Plattformen implementiert werden müssen, um als [.NET Standard](../../standard/library.md)-Plattform zu gelten.

**Microsoft.NETCore.App**

- v1.0 ab .NET Core 1.0 (diese Versionen werden übereinstimmen)
- Ist dem `netcoreapp`-Framework zugeordnet
- Beschreibt die Pakete in der .NET Core-Verteilung

Hinweis: [`Microsoft.NETCore.Portable.Compatibility`](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility) ist ein weiteres .NET Core-Metapaket. Es wird keinem bestimmten Framework zugeordnet und wird daher wie ein Paket versioniert.

### <a name="frameworks"></a>Frameworks

Framework-Versionen werden aktualisiert, wenn neue APIs hinzugefügt werden. Sie verfügen über kein Konzept der Patchversion, da sie die API-Form und keine Implementierungsprobleme darstellen. Die Haupt- und Nebenversionskontrolle befolgt die zuvor angegebenen SemVer-Regeln.

Das `netcoreapp`-Framework ist an die .NET Core-Verteilung gebunden. Es befolgt die Versionsnummern, die von .NET Core verwendet werden. Wenn z.B. .NET Core 2.0 veröffentlicht wird, wird es auf `netcoreapp2.0` abzielen. Das `netstandard`-Framework entspricht nicht dem Schema der Versionierung einer beliebigen .NET-Laufzeit, vorausgesetzt, dass es gleichmäßig auf alle Laufzeiten angewendet werden kann.

## <a name="versioning-in-practice"></a>Versionskontrolle in der Praxis

Es gibt täglich Commits und PRs auf .NET Core-Repositorys auf GitHub, wodurch viele Bibliotheken neue Builds erhalten. Es ist nicht sehr praktisch, neue öffentliche .NET Core-Versionen für jede Änderung zu erstellen. Stattdessen werden die Änderungen über einen grob definierten Zeitraum (z.B. Wochen oder Monate) aggregiert, bevor eine neue, öffentliche stabile .NET Core-Version erstellt wird.

Eine neue Version von .NET Core bringt Folgendes mit sich:

- Neue Versionen von Paketen und Metapaketen
- Neue Versionen von verschiedenen Frameworks, vorausgesetzt, neue APIs werden hinzugefügt
- Neue Version der .NET Core-Verteilung

### <a name="shipping-a-patch-release"></a>Versand einer Patchversion

Nach der Auslieferung einer stabilen Version von .NET Core v1.0.0, werden keine Änderungen auf Patchebene (keine neuen APIs) an .NET Core-Bibliotheken zur Behebung von Fehlern und zur Verbesserung der Leistung sowie der Zuverlässigkeit vorgenommen. Die verschiedenen Metapakete werden aktualisiert, um auf die aktualisierten .NET Core-Bibliothekspakete zu verweisen. Die Metapakete werden als Patchupdates (x.y.z) versioniert. Frameworks werden nicht aktualisiert. Eine neue .NET Core-Verteilung wird mit einer übereinstimmenden Versionsnummer für das Metapaket `Microsoft.NETCore.App` freigegeben.

Im folgenden project.json-Beispiel werden Patchupdates dargestellt.

```
{
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.1"
  },
  "frameworks": {
    "netcoreapp1.0": {}
  }
}
```

### <a name="shipping-a-minor-release"></a>Versenden einer Nebenversion

Nach der Auslieferung einer stabilen NET Core v1.0.0-Version, werden neue APIs den .NET Core-Bibliotheken hinzugefügt, sodass neue Szenarios aktiviert werden. Die verschiedenen Metapakete werden aktualisiert, um auf die aktualisierten .NET Core-Bibliothekspakete zu verweisen. Die Metapakete werden als Patchupdates (x.y) versioniert, um mit den höheren Frameworkversionen übereinzustimmen. Die verschiedenen Frameworks werden aktualisiert, um die neuen APIs zu beschreiben. Eine neue .NET Core-Verteilung wird mit einer übereinstimmenden Versionsnummer für das Metapaket `Microsoft.NETCore.App` freigegeben.

In der folgenden Projektdatei werden geringfügige Updates veranschaulicht:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp1.1</TargetFramework>
  </PropertyGroup>
</Project>
```

### <a name="shipping-a-major-release"></a>Versenden einer Hauptversion

Mit einer stabilen NET Core v1.y.z-Version werden neue APIs den .NET Core-Bibliotheken hinzugefügt, sodass umfangreiche neue Szenarios aktiviert werden. Möglicherweise wird die Unterstützung für eine Plattform verworfen. Die verschiedenen Metapakete werden aktualisiert, um auf die aktualisierten .NET Core-Bibliothekspakete zu verweisen. Das Metapaket `Microsoft.NETCore.App` und das `netcore`-Framework werden als wichtiges Update (x) versioniert. Das Metapaket `NETStandard.Library` wird wahrscheinlich als geringfügiges Update (x.y) versioniert, da es für mehrere .NET-Implementierungen gilt. Eine neue .NET Core-Verteilung würde mit einer übereinstimmenden Versionsnummer für das Metapaket `Microsoft.NETCore.App` freigegeben werden.

In der folgenden Projektdatei werden größere Updates veranschaulicht. (Beachten Sie, dass `netcoreapp2.0` nicht freigegeben wurde.)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp2.0</TargetFramework>
  </PropertyGroup>
</Project>
```

