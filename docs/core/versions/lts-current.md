---
title: .NET Core-Unterstützung
description: Informationen über die Unterstützung der unterschiedlichen Releasepläne (LTS und Current) für .NET Core
author: kendrahavens
ms.author: mairaw
ms.date: 01/30/2017
ms.openlocfilehash: b61aa48451cee60be4968c151b97746a3aef85c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="net-core-support"></a>.NET Core-Unterstützung

Dies ist eine allgemeine Beschreibung der .NET Core-Unterstützung.

## <a name="lts-and-current-release-trains"></a>LTS- und Current-Releasepläne

In der gesamten Softwarewelt ist es ein gängiges Konzept, zwei Releasepläne für Unterstützung zu haben. Dies gilt insbesondere für Open-Source-Projekte wie .NET Core. .NET Core hat die folgenden Releasepläne für Unterstützung: [Long Term Support (LTS)](https://en.wikipedia.org/wiki/Long-term_support) und Current. LTS-Releases werden in ihrem gesamten Lebenszyklus hinsichtlich Stabilität gewartet und erhalten Korrekturen für wesentliche Probleme sowie Sicherheitsupdates. Das Arbeiten an neuen Funktionen und zusätzliche Fehlerbehebungen erfolgen in Current-Releases. Aus Unterstützungssicht haben diese Releasepläne die folgenden Attribute für einen Unterstützungslebenszyklus.

Für LTS-Releases gilt Folgendes:
* Sie werden für einen Zeitraum von drei Jahren ab dem allgemeinen Verfügbarkeitsdatum eines LTS-Release unterstützt.
* Oder sie werden für einen Zeitraum von einem Jahr ab der allgemeinen Verfügbarkeit eines späteren LTS-Release unterstützt.

Für Current-Releases gilt Folgendes:
* Sie werden im selben Dreijahreszeitraum unterstützt wie das übergeordnete LTS-Release.
* Sie werden drei Monate lang ab der allgemeinen Verfügbarkeit eines späteren Current-Release unterstützt.
* Und sie werden ein Jahr lang ab der allgemeinen Verfügbarkeit eines späteren LTS-Release unterstützt.

## <a name="versioning"></a>Versionskontrolle
Ein neues LTS-Release ist durch eine Erhöhung der Hauptversionsnummer gekennzeichnet. Ein Current-Release hat dieselbe Hauptversionsnummer wie der entsprechende LTS-Plan und ist durch eine Erhöhung der Nebenversionsnummer gekennzeichnet. Beispielsweise wäre 1.0.3 LTS und 1.1.0 Current. Fehlerkorrekturupdates für einen dieser Pläne bewirken, dass die Patchversion erhöht wird. Weitere Informationen über das Versionsschema finden Sie unter [.NET Core Versioning](index.md).

## <a name="what-causes-updates-in-lts-and-current-trains"></a>Wodurch werden Updates in LTS- und Current-Releases ausgelöst?
Um zu verstehen, welche speziellen Änderungen, etwa Fehlerbehebungen oder das Hinzufügen von APIs, Aktualisierungen der Versionsnummern auslösen, sollten Sie den Abschnitt „Decision Tree“ (Entscheidungsbaum) in der [Versioning Documentation](index.md) (Dokumentation zur Versionsverwaltung) lesen. Es ist keine goldenen Regeln, anhand denen entschieden wird, welche Änderungen aus Current in den LTS-Zweig übernommen werden. Normalerweise sind erforderliche Sicherheitsupdates und Patches, die zu erwartetem Verhalten führen, Gründe dafür, den LTS-Zweig zu aktualisieren. Es ist außerdem beabsichtigt, neuere Betriebssysteme für Desktopentwickler im LTS-Zweig zu unterstützen, obwohl dies möglicherweise nicht immer möglich sein wird. Eine gute Möglichkeit, mehr darüber zu erfahren, welche APIs, Fehlerbehebungen und Betriebssysteme in einem bestimmten Release unterstützt werden, besteht darin, dessen [Release Notes](https://github.com/dotnet/core/tree/master/release-notes) auf GitHub zu durchsuchen.

### <a name="further-reading"></a>Weiterführende Themen
* [.NET Core Support Lifecycle Fact Sheet](https://www.microsoft.com/net/core/support)
* [Derzeit unterstützte Betriebssysteme und Versionen](https://github.com/dotnet/core/blob/master/roadmap.md)
