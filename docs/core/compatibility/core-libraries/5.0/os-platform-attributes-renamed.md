---
title: 'Breaking Change: OSPlatform-Attribute umbenannt oder entfernt'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den die in einer Vorschauversion eingeführten Betriebssystem-Plattformattribute entfernt oder umbenannt wurden.
ms.date: 11/01/2020
ms.openlocfilehash: be2ddd4909bef70f531ca48246f091923d6435ec
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739489"
---
# <a name="osplatform-attributes-renamed-or-removed"></a>OSPlatform-Attribute umbenannt oder entfernt

Die folgenden Attribute, die in .NET 5.0 Preview 8 eingeführt wurden, wurden entfernt oder umbenannt: `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute` und `ObsoletedInOSPlatformAttribute`.

## <a name="change-description"></a>Änderungsbeschreibung

In NET 5.0 Preview 8 wurden die folgenden Attribute im Namespace <xref:System.Runtime.Versioning> eingeführt:

- `MinimumOSPlatformAttribute`
- `RemovedInOSPlatformAttribute`
- `ObsoletedInOSPlatformAttribute`

Wenn in .NET 5.0 Preview 8 ein Projekt auf eine betriebssystemspezifische Variante von .NET 5 abzielt, indem ein [Zielframeworkmoniker](../../../../standard/frameworks.md) wie z. B. `net5.0-windows` verwendet wird, fügt der Build das Attribut `System.Runtime.Versioning.MinimumOSPlatformAttribute` auf Assembly-Ebene hinzu.

In .NET 5.0 RC1 wurde `ObsoletedInOSPlatformAttribute` entfernt, und `MinimumOSPlatformAttribute` und `RemovedInOSPlatformAttribute` wurden wie folgt umbenannt:

| Name in Preview 8 | Name ab RC1 |
| - | - |
| `MinimumOSPlatformAttribute` | <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> |
| `RemovedInOSPlatformAttribute` | <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> |

Wenn ab .NET 5.0 RC1 ein Projekt auf eine betriebssystemspezifische Variante von .NET 5 abzielt, indem ein [Zielframeworkmoniker](../../../../standard/frameworks.md) wie z. B. `net5.0-windows` verwendet wird, fügt der Build das Attribut <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> auf Assembly-Ebene hinzu.

## <a name="reason-for-change"></a>Grund für die Änderung

In NET 5.0 Preview 8 wurden Attribute in <xref:System.Runtime.Versioning> eingeführt, um unterstützte Plattformen für APIs anzugeben. Die Attribute werden vom [Analysetool für die Plattformkompatibilität](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) genutzt, um Buildwarnungen zu erzeugen, wenn plattformspezifische APIs auf Plattformen eingesetzt werden, die diese APIs nicht unterstützen.

In .NET 5.0 RC1 wurde dem Analysetool für die Plattformkompatibilität ein zusätzliches Feature für den Ausschluss von Plattformen hinzugefügt. Diese Feature ermöglicht, dass APIs auf Betriebssystemplattformen als gänzlich nicht unterstützt markiert werden. Dieses Feature hat Änderungen an den Attributen veranlasst, einschließlich der Verwendung geeigneterer Namen. `ObsoletedInOSPlatformAttribute` wurde entfernt, da es nicht mehr benötigt wird.

## <a name="version-introduced"></a>Eingeführt in Version

5.0 RC1

## <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie Ihr Projekt von .NET 5.0 Preview 8 auf .NET 5.0 RC1 umstellen, kann es aufgrund dieser Änderungen zu Build- oder Laufzeitfehlern kommen. Beispielsweise führt die Umbenennung von `MinimumOSPlatformAttribute` wahrscheinlich zu Fehlern, da das Attribut zur Buildzeit auf plattformspezifische Assemblys angewendet wird und alte Buildartefakte weiterhin auf den alten API-Namen verweisen.

Beispiele für Fehler zur Buildzeit:

- **Fehler CS0246: Der Typ- oder Namespacename MinimumOSPlatformAttribute wurde nicht gefunden (fehlt eine using-Direktive oder ein Assemblyverweis?)**
- **Fehler CS0246: Der Typ- oder Namespacename RemovedInOSPlatformAttribute wurde nicht gefunden (fehlt eine using-Direktive oder ein Assemblyverweis?)**
- **Fehler CS0246: Der Typ- oder Namespacename ObsoletedInOSPlatformAttribute wurde nicht gefunden (fehlt eine using-Direktive oder ein Assemblyverweis?)**

Beispiel für Laufzeitfehler:

**„Unbehandelte Ausnahme. System.TypeLoadException: Der Typ System.Runtime.Versioning.MinimumOSPlatformAttribute konnte nicht aus Assembly System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a geladen werden.**

So beheben Sie diese Fehler

- Ändern Sie alle Verweise auf `MinimumOSPlatformAttribute` in <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>.
- Ändern Sie alle Verweise auf `RemovedInOSPlatformAttribute` in <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>.
- Entfernen Sie alle Verweise auf `ObsoletedInOSPlatformAttribute`.
- Erstellen Sie Ihr Projekt neu (oder führen Sie Bereinigung und Build durch), um alte Buildartefakte zu löschen.

## <a name="affected-apis"></a>Betroffene APIs

- `System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `System.Runtime.Versioning.RemovedInOSPlatformAttribute`

<!--

### Category

Core .NET libraries

### Affected APIs

- `T:System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `T:System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `T:System.Runtime.Versioning.RemovedInOSPlatformAttribute`

-->
