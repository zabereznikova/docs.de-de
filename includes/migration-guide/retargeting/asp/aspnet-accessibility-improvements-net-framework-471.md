---
ms.openlocfilehash: 418bcdca1e9a325894891d7b0e080ce035e2d1b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614458"
---
### <a name="aspnet-accessibility-improvements-in-net-framework-471"></a>Verbesserungen der Barrierefreiheit von ASP.NET in .NET Framework 4.7.1

#### <a name="details"></a>Details

Ab .NET Framework 4.7.1 arbeiten .ASP.NET-Websteuerelemente effizienter mit den Funktionen für die Barrierefreiheit in Visual Studio zusammen, wodurch ASP.NET-Kunden besser unterstützt werden.  Folgende Änderungen wurden u.a. vorgenommen:

- Änderungen, durch die fehlende Barrierefreiheitsmuster für Steuerelemente der Benutzeroberfläche implementiert werden. Zu diesen Steuerelementen zählen z.B. das Dialogfeld „Feld hinzufügen“ im Detailansicht-Assistenten oder das Dialogfeld „ListView konfigurieren“ im ListView-Assistenten.
- Änderungen zur Verbesserung der Anzeige im Modus für hohe Kontraste, z.B. beim DataPager-Feld-Editor.
- Änderungen zur Verbesserung der Benutzerfreundlichkeit bei der Tastaturnavigation für Steuerelemente, z.B. beim Dialogfeld „Felder“ im Assistenten für das Bearbeiten von Pagerfeldern des DataPager-Steuerelements, beim Dialogfeld „ObjectContext konfigurieren“ oder beim Dialogfeld „Datenauswahl konfigurieren“ des Assistenten zum Konfigurieren der Datenquelle.

#### <a name="suggestion"></a>Vorschlag

**Aktivieren oder Deaktivieren dieser Änderungen:** Damit diese Änderungen in Visual Studio Designer eingesetzt werden können, muss das Tool unter .NET Framework 4.7.1 oder höher ausgeführt werden. Die Webanwendung kann diese Änderungen nutzen, wenn Sie folgende Schritte durchführen:

- Installieren Sie Visual Studio 2017 15.3 oder höher. Ab dieser Version werden die neuen Barrierefreiheitsfeatures mit der unten aufgeführten AppContext-Option standardmäßig unterstützt.
- Deaktivieren Sie die Legacy-Barrierefreiheitsverhalten, indem Sie in der Konfigurationsdatei „devenv.exe“ dem Abschnitt `<runtime>` die AppContext-Option `Switch.UseLegacyAccessibilityFeatures` hinzufügen und sie auf `false` festlegen, wie im folgenden Beispiel dargestellt wird.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
<runtime>
...
<!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false'  -->
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
...
</runtime>
</configuration>
```

Bei Anwendungen, die .NET Framework 4.7.1 oder höher als Zielplattform verwenden und die Legacy-Barrierefreiheitsverhalten beibehalten sollen, können Sie die Verwendung des veralteten Features für die Barrierefreiheit aktivieren, indem Sie die AppContext-Option auf `true` festlegen.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7.1       |
| Typ    | Neuzuweisung |
