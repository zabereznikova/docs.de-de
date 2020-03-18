---
ms.openlocfilehash: c8f44ae1a500ed240dbff7d9a2c1479af368b7f1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394050"
---
### <a name="identity-default-bootstrap-version-of-ui-changed"></a>Identität: Bootstrap-Standardversion der Benutzeroberfläche geändert

Ab ASP.NET Core 3.0 verwendet die Identitäts-Benutzeroberfläche standardmäßig Version 4 von Bootstrap.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Der `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();`-Methodenaufruf war mit `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);` identisch.

#### <a name="new-behavior"></a>Neues Verhalten

Der `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();`-Methodenaufruf ist mit `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);` identisch.

#### <a name="reason-for-change"></a>Grund für die Änderung

Bootstrap 4 wurde im Zeitrahmen von ASP.NET Core 3.0 veröffentlicht.

#### <a name="recommended-action"></a>Empfohlene Aktion

Diese Änderung hat Auswirkungen auf Ihre Arbeit, wenn Sie die Standardbenutzeroberfläche für Identitäten verwenden und diese in `Startup.ConfigureServices` hinzugefügt haben, wie im folgenden Beispiel gezeigt:

```csharp
services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();
```

Führen Sie eine der folgenden Aktionen aus:

- Migrieren Sie Ihre App mithilfe der [Migrationsanleitung](https://getbootstrap.com/docs/4.0/migration) zur Verwendung von Bootstrap 4.
- Aktualisieren Sie `Startup.ConfigureServices`, um die Verwendung von Bootstrap 3 zu erzwingen. Zum Beispiel:

    ```csharp
    services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);
    ```

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
