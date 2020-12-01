---
ms.openlocfilehash: 7a2617f27dfd6bb527ff6d408fae6382075f24ae
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032152"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a>TypeDescriptionProviderAttribute in andere Assembly verschoben

Die <xref:System.ComponentModel.TypeDescriptionProviderAttribute>-Klasse wurde verschoben.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 2.2 und früheren Versionen befand sich die <xref:System.ComponentModel.TypeDescriptionProviderAttribute>-Klasse in der *System.ComponentModel.TypeConverter*-Assembly.

Seit .NET Core 3.0 befindet sie sich in der *System.ObjectModel*-Assembly.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Diese Änderung betrifft nur Anwendungen, welche die Reflektion zum Laden des <xref:System.ComponentModel.TypeDescriptionProviderAttribute>-Typs durch Aufrufen einer Methode wie <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> oder eine Überladung von <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> nutzen, bei der vorausgesetzt wird, dass sich der Typ in einer bestimmten Assembly befindet. Ist dies der Fall, muss die im Methodenaufruf referenzierte Assembly entsprechend dem neuen Assemblyspeicherort des Typs aktualisiert werden.

#### <a name="category"></a>Kategorie

Windows Forms

#### <a name="affected-apis"></a>Betroffene APIs

Keine.

<!--

#### Affected APIs

- Not detectable via API analysis

-->
