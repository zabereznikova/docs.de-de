---
title: .NET-Releases, -Patches und -Support
description: Hier erfahren Sie mehr über Releases, Patches und Support für .NET 5 (einschließlich .NET Core) und höhere Versionen.
ms.date: 10/07/2020
ms.topic: overview
ms.author: tdykstra
author: tdykstra
ms.openlocfilehash: 896b88cbf1f7f31d2d26d69ec7d219da6b27ceff
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "97866390"
---
# <a name="releases-and-support-for-net-core-and-net-5"></a>Releases und Support für .NET Core und .NET 5

Microsoft veröffentlicht wichtige Releases, Nebenversionen und Wartungsupdates (Patches) für .NET 5.0 (und .NET Core) und spätere Versionen. In diesem Artikel werden Releasetypen, Wartungsupdates, SDK-Featuregruppen, Supportzeiträume und Supportoptionen erläutert.

## <a name="release-types"></a>Releasetypen

Informationen zur Art der einzelnen Releases werden in der Versionsnummer in der Form *Hauptversion.Nebenversion.Patch* angegeben.

Beispiel:

* .NET Core 3.0 und .NET 5.0 sind Hauptversionen.
* .NET Core 3.1 ist die erste Nebenversion nach der Hauptversion von .NET Core 3.0.
* .NET Core 3.1.7 ist der siebte Patch für .NET Core 3.1.

### <a name="major-releases"></a>Hauptversionen

Zu den Hauptversionen zählen neue Features, neue Oberflächenbereiche für die öffentliche API und Fehlerbehebungen. Beispiele hierfür sind .NET Core 3.0 und .NET 5.0.  Aufgrund der Art der Änderungen ist es wahrscheinlich, dass diese Versionen zu Breaking Changes führen. Hauptversionen können neben früheren Hauptversionen installiert werden.

### <a name="minor-releases"></a>Nebenversionen

Nebenversionen umfassen auch neue Features, neue Oberflächenbereiche für die öffentliche API und Fehlerbehebungen und können auch zu Breaking Changes führen. Beispiele hierfür sind .NET Core 2.1 und .NET Core 3.1. Der Unterschied zwischen Nebenversionen und Hauptversionen besteht im Ausmaß der Änderungen. In Nebenversionen ist dieses geringer. Eine Anwendung, die von .NET Core 3.0 auf 3.1 aktualisiert wird, weist nur geringfügige Änderungen auf, die wenig Anpassungen erfordern. Nebenversionen können neben früheren Nebenversionen installiert werden.

### <a name="servicing-updates"></a>Wartungsaktualisierungen

Wartungsupdates (Patches) werden fast jeden Monat veröffentlicht. Diese Updates enthalten sowohl sicherheitsrelevante als auch sicherheitsirrelevante Fehlerkorrekturen. Beispielsweise ist .NET Core 3.1.8 das achte Update für .NET Core 3.1. Wenn diese Updates Sicherheitskorrekturen enthalten, werden Sie am sogenannten "Patch Tuesday" veröffentlicht. Das ist immer der zweite Dienstag des Monats. Wartungsupdates gewährleisten normalerweise die Kompatibilität. Ab .NET Core 3.1 sind Wartungsupdates Upgrades, durch die das vorherige Update entfernt wird. Beispielsweise entfernt das letzte Wartungsupdate für .NET Core 3.1 das vorherige Update nach erfolgreicher Installation.

### <a name="feature-bands-sdk-only"></a>Featuregruppen (nur SDK)

Die Versionsverwaltung für das .NET SDK funktioniert etwas anders als für die .NET-Runtime. .NET SDK-Updates enthalten unter Umständen neue Features oder neue Komponentenversion wie MSBuild oder NuGet, um bestmöglich zu Visual Studio-Releases zu passen. Diese neuen Features oder Komponenten sind möglicherweise nicht mit den Versionen kompatibel, die in vorherigen SDK-Updates für dieselbe Haupt- oder Nebenversion ausgeliefert wurden.

Das .NET SDK verwendet Featuregruppen, um solche Updates zu kennzeichnen. Das erste .NET Core 3.1 SDK war beispielsweise 3.1.100. Dieses Release entspricht der Featuregruppe *3.1.1xx*. Featuregruppen werden in den Hundertergruppen im dritten Teil der Versionsnummer definiert. Die Versionen 3.1.101 und 3.1.201 sind beispielsweise Versionen in zwei verschiedenen Featuregruppen, während sich 3.1.101 und 3.1.199 in derselben Featuregruppe befinden. Wenn das .NET Core SDK 3.1.101 installiert wird, wird das .NET Core SDK 3.1.100 (sofern vorhanden) vom Computer entfernt. Wenn das .NET Core SDK 3.1.200 auf demselben Computer installiert ist, wird das .NET Core SDK 3.1.101 nicht entfernt.

### <a name="runtime-roll-forward-and-compatibility"></a>Rollforward und Kompatibilität der Runtime

Wichtige und kleinere Updates werden neben früheren Versionen installiert. Eine Anwendung, die für eine bestimmte *Hauptversion. Nebenversion*-Version erstellt wurde, verwendet weiterhin diese Zielruntime, auch wenn eine neuere Version installiert ist. Die App führt nicht automatisch ein Rollforward aus, um eine neuere *Hauptversion.Nebenversion*-Version der Laufzeit zu verwenden, es sei denn, Sie entscheiden sich für dieses Verhalten. Eine Anwendung, die für .NET Core 3.0 erstellt wurde, wird nicht automatisch in .NET Core 3.1 ausgeführt. Es wird empfohlen, die App neu zu erstellen und vor der Bereitstellung in der Produktion mit einer neueren Haupt- oder Nebenversion der Runtime zu testen. Weitere Informationen finden Sie unter [Rollforward für von Frameworks abhängigen Apps](versions/selection.md#framework-dependent-apps-roll-forward) und [Rollforward für eine eigenständige Bereitstellungsruntime](deploying/runtime-patch-selection.md).

Wartungsupdates werden von Haupt- und Nebenversionen anders behandelt. Eine Anwendung, die auf .NET Core 3.1 ausgerichtet ist, wird standardmäßig in der 3.1.0-Runtime ausgeführt. Es wird automatisch ein Rollforward ausgeführt, um eine neuere Runtimeversion 3.1.1 zu verwenden, wenn dieses Wartungsupdate installiert wird. Dieses Verhalten ist die Standardeinstellung, da Sicherheitskorrekturen verwendet werden sollen, sobald Sie installiert werden, ohne dass weitere Aktionen erforderlich sind. Sie können dieses standardmäßige Rollforwardverhalten ablehnen.

## <a name="net-core-and-net-5-version-lifecycles"></a>Versionslebenszyklen von .NET Core und .NET 5

.NET Core, .NET 5 und höhere Versionen unterliegen den [Modern Lifecycle-Richtlinien](/lifecycle/policies/modern), und nicht den [Fixed Lifecycle-Richtlinien](/lifecycle/policies/fixed), die für .NET Framework-Releases galten. Produkte mit einem festen Lebenszyklus haben einen langen, feststehenden Zeitraum, in dem der Support gewährleistet wird. Das können z. B. fünf Jahre Mainstream-Support und weitere fünf Jahre erweiterter Support sein. Mainstream-Support umfasst sicherheitsrelevante und nicht sicherheitsrelevante Korrekturen, während der erweiterte Support nur Sicherheitskorrekturen bereitstellt. Produkte mit einem modernen Lebenszyklus haben ein Supportmodell, das dem eine Diensts ähnelt, mit einem kürzeren Supportzeitraum und häufigeren Releases.

### <a name="release-tracks"></a>Releasearten

Es gibt zwei Supportarten für Releases:

* *Aktuelle* Releases

  Diese Versionen werden bis zu drei Monate nach der Veröffentlichung der nächsten Haupt- oder neben Version unterstützt.

  Beispiel:

  * .NET Core 3.0 wurde im September 2019 veröffentlicht, gefolgt von .NET Core 3.1 im Dezember 2019.
  * Der .NET Core 3.0-Support endete im März 2020, drei Monate nach der Veröffentlichung von Version 3.1.

* *Long Term Support-* Releases (LTS)

  Diese Versionen erhalten mindestens drei Jahre lang Support, oder ein Jahr nach der Auslieferung des nächsten LTS-Releases, wenn dieses Datum nach dem Zeitraum von drei Jahren liegt.

  Beispiel:

  * .NET Core 2.1 wurde im Mai 2018 veröffentlicht und im August 2018 als LTS-Release eingestuft.
  * .NET Core 3.1 war der nächste LTS-Release und wurde im Dezember 2019 veröffentlicht.
  * Da August 2021 (drei Jahre) nach Dezember 2020 (ein Jahr nach der Version 3.1) kommt, erhält .NET Core 2.1 bis August 2021 Support.

Releases werden abwechselnd als LTS- und Current-Releases veröffentlicht, sodass ein früheres Release länger als ein späteres Release Support erhalten kann. .NET Core 2.1 ist z. B. eine LTS-Version mit Unterstützung bis August 2021. Das 3.0-Release wurde mehr als ein Jahr später veröffentlicht, aber der Support wurde bereits im Dezember 2019 eingestellt.

Wartungsupdates werden monatlich veröffentlicht und enthalten sowohl Sicherheits- als auch nicht sicherheitsrelevante Korrekturen (Zuverlässigkeit, Kompatibilität und Stabilität). Wartungsupdates werden unterstützt, bis das nächste Wartungsupdate veröffentlicht wird. Wartungsupdates nutzen Runtimerollforwards. Dies bedeutet, dass Anwendungen standardmäßig mit dem zuletzt installierten Runtimewartungsupdate ausgeführt werden.

## <a name="how-to-choose-a-release"></a>Auswählen eines Releases

Wenn Sie einen Dienst erstellen und davon ausgehen, dass er regelmäßig aktualisiert werden wird, ist eine aktuelle Version wie .NET 5.0 die beste Option, um bei den neuesten Features von .NET immer auf dem neuesten Stand zu sein.

Wenn Sie eine Clientanwendung entwickeln, die an Consumer verteilt wird, kann es sein, dass die Stabilität wichtiger ist als der Zugriff auf die neuesten Features. Es kann erforderlich sein, dass Support für die Anwendung für einen bestimmten Zeitraum gewährleistet ist, bevor der Consumer ein Upgrade auf die nächste Version der Anwendung durchführen kann. In diesem Fall kann eine LTS-Version wie .NET Core 3.1 die richtige Option sein.

### <a name="servicing-updates"></a>Wartungsaktualisierungen

.NET-Wartungsupdates weisen Support auf, bis das nächste Wartungsupdate veröffentlicht wird. Releases werden monatlich veröffentlicht.

Sie müssen regelmäßig Wartungsupdates installieren, um sicherzustellen, dass sich Ihre Apps in einem sicheren Zustand mit Support befinden. Wenn beispielsweise das neueste Wartungsupdate für .NET Core 3.1 Version 3.1.8 ist und Version 3.1.9 veröffentlicht wird, ist Version 3.1.8 nicht mehr die neueste. Der unterstützte Wartungsupdate für Version 3.1 ist dann 3.1.9.

Informationen zu den neuesten Wartungsupdates für jede Haupt- und Nebenversion finden Sie auf der [.NET-Downloadseite](https://dotnet.microsoft.com/download/dotnet-core).

## <a name="end-of-support"></a>Ende des Supports

Das Ende des Supports bezieht sich auf das Datum, nach dem Microsoft keine Korrekturen, Updates oder technische Unterstützung für eine Produktversion mehr bereitstellt. Stellen Sie sicher, dass Sie vor diesem Datum zu einer unterstützten Version wechseln. Versionen, für die kein Support mehr bereitgestellt wird, erhalten keine Sicherheitsupdates mehr, die Ihre Anwendungen und Daten schützen.

## <a name="supported-operating-systems"></a>Unterstützte Betriebssysteme

.NET 5 (und .NET Core) und spätere Versionen können unter verschiedenen Betriebssystemen ausgeführt werden. Jedes dieser Betriebssysteme verfügt über einen Lebenszyklus, der von seiner Sponsororganisation (z. B. Microsoft, Red Hat oder Apple) definiert wird. Diese Lebenszyklus-Zeitpläne werden beim Hinzufügen und Entfernen des Supports für Betriebssystemversionen berücksichtigt.

Wenn eine Betriebssystemversion keinen Support mehr erhält, wird die Version nicht mehr getestet und der Support wird eingestellt. Benutzer müssen auf eine unterstützte Betriebssystemversion umsteigen, um Support zu erhalten.

Weitere Informationen finden Sie unter [.NET-Betriebssystem-Lebenszyklus-Richtlinie](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md).

## <a name="get-support"></a>Support

Sie haben die Wahl zwischen Microsoft-Support und Communitysupport.

### <a name="microsoft-support"></a>Microsoft-Support

[Wenden Sie sich an einen Microsoft-Supportmitarbeiter](https://support.microsoft.com/supportforbusiness/productselection/?sapid=4fd4947b-15ea-ce01-080f-97f2ca3c76e8), um Support zu erhalten.

Sie müssen ein unterstütztes Wartungsupdate installiert haben (das neueste verfügbare Wartungsupdate), um Support zu erhalten. Wenn auf einem System Version 3.1 ausgeführt wird und das Wartungsupdate 3.1.8 veröffentlicht wurde, muss Version 3.1.8 als Erstes installiert werden.

### <a name="community-support"></a>Communityunterstützung

Informationen zum Communitysupport finden Sie unter [Community](https://dotnet.microsoft.com/platform/community).

## <a name="see-also"></a>Siehe auch

Weitere Informationen einschließlich der unterstützten Datumsbereiche für jede Version von .NET Core und für .NET 5 finden Sie in der [Support-Richtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).
