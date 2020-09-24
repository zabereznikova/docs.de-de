---
title: Featureflags
description: Implementieren von featureflags in Cloud-native Anwendungen mit Azure-app config
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: ee45c9f187b056887ea6dd3a08da508afca51987
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158096"
---
# <a name="feature-flags"></a>Featureflags

In Kapitel 1 haben wir bestätigt, dass Cloud Native sehr viel über Geschwindigkeit und Agilität verfügt. Benutzer erwarten schnelle Reaktionsfähigkeit, innovative Features und keine Ausfallzeiten. `Feature flags` bei handelt es sich um ein modernes Bereitstellungs Verfahren, mit dem sich die Agilität von cloudbasierten Anwendungen erhöhen lässt Sie ermöglichen es Ihnen, neue Features in einer Produktionsumgebung bereitzustellen, aber die Verfügbarkeit einzuschränken. Mit der flicke eines Schalters können Sie ein neues Feature für bestimmte Benutzer aktivieren, ohne die APP neu zu starten oder neuen Code bereitzustellen. Sie trennen die Freigabe neuer Features von ihrer Code Bereitstellung.

Merkmals Flags basieren auf einer bedingten Logik, die die Sichtbarkeit von Benutzern zur Laufzeit steuert. In modernen, cloudbasierten Systemen ist es üblich, neue Features frühzeitig in der Produktion bereitzustellen, Sie aber mit einer begrenzten Zielgruppe zu testen. Wenn das Vertrauen zunimmt, kann die Funktion inkrementell für größere Zielgruppen eingeführt werden.

Weitere Anwendungsfälle für Merkmals Flags sind:

- Beschränken Sie die Premium-Funktionalität auf bestimmte Kundengruppen, die zur Zahlung höherer Abonnementgebühren bereit sind.
- Stabilisieren Sie ein System, indem Sie eine Problem Funktion schnell deaktivieren und so die Risiken eines Rollbacks oder sofortigen Hotfixes vermeiden.
- Deaktivieren Sie ein optionales Feature mit hohem Ressourcenverbrauch während der Spitzenzeiten.
- Durchführen `experimental feature releases` von kleinen Benutzer Segmenten zum Überprüfen der Durchführbarkeit und Beliebtheit

Merkmals Flags fördern auch die `trunk-based` Entwicklung. Dabei handelt es sich um ein Branchen Modell zur Quell Code Verwaltung, in dem Entwickler an Features in einer einzelnen Verzweigung zusammenarbeiten. Der Ansatz minimiert das Risiko und die Komplexität der Zusammenführung einer großen Anzahl von featurebranches mit langer Laufzeit. Die Funktionen sind bis zur Aktivierung nicht verfügbar.

## <a name="implementing-feature-flags"></a>Implementieren von featureflags

Im Kern ist ein Merkmals Flag ein Verweis auf einen einfachen `decision object` . Sie gibt einen booleschen Zustand von `on` oder zurück `off` . Das Flag umschließt in der Regel einen Codeblock, der eine featurefunktion kapselt. Der Status des Flags bestimmt, ob dieser Codeblock für einen bestimmten Benutzer ausgeführt wird. In Abbildung 10-11 wird die Implementierung veranschaulicht.

```csharp
if (featureFlag) {
    // Run this code block if the featureFlag value is true
} else {
    // Run this code block if the featureFlag value is false
}
```

**Abbildung 10-11** -einfache Implementierung von featureflags.

Beachten Sie, dass diese Vorgehensweise die Entscheidungs Logik von dem Funktionscode trennt.

In Kapitel 1 wurde erläutert `Twelve-Factor App` . Es wird empfohlen, Konfigurationseinstellungen Extern aus dem ausführbaren Code der Anwendung zu speichern. Bei Bedarf können die Einstellungen aus der externen Quelle gelesen werden. Merkmals Flag-Konfigurationswerte sollten auch unabhängig von Ihrer Codebasis sein. Durch externalisieren der Flag-Konfiguration in einem separaten Repository können Sie den Flag-Status ändern, ohne die Anwendung zu ändern und erneut bereitzustellen.

[Azure-App Konfiguration](/azure/azure-app-configuration/overview) stellt ein zentralisiertes Repository für Merkmals Flags bereit. Mit dieser Funktion definieren Sie verschiedene Arten von featureflags und ändern ihre Zustände schnell und zuverlässig. Sie fügen der Anwendung die Client Bibliotheken für die APP-Konfiguration hinzu, um Feature-Flag-Funktionen zu aktivieren. Verschiedene Frameworks für Programmiersprachen werden unterstützt.

Merkmals Flags können problemlos in einem [ASP.net Core-Dienst](/azure/azure-app-configuration/use-feature-flags-dotnet-core)implementiert werden. Durch die Installation der .net-funktionsverwaltungs-Bibliotheken und des App-Konfigurations Anbieters können Sie Ihrem Code deklarativ Merkmals Flags hinzufügen. Sie aktivieren `FeatureGate` Attribute, sodass Sie nicht manuell if-Anweisungen in Ihre CodeBase schreiben müssen.

Nachdem Sie in der Startup-Klasse konfiguriert wurde, können Sie Feature-Flag-Funktionalität auf Controller-, Aktions-oder Middleware-Ebene hinzufügen. In Abbildung 10-12 wird die Implementierung von Controller und Aktion dargestellt:

```csharp
[FeatureGate(MyFeatureFlags.FeatureA)]
public class ProductController : Controller
{
    ...
}
```

```csharp
[FeatureGate(MyFeatureFlags.FeatureA)]
public IActionResult UpdateProductStatus()
{
    return ObjectResult(ProductDto);
}
```

**Abbildung 10-12** : Implementierung von featureflags in einem Controller und einer Aktion.

Wenn ein Merkmals Flag deaktiviert ist, empfängt der Benutzer den Statuscode 404 (nicht gefunden) ohne Antworttext.

Merkmals Flags können auch direkt in c#-Klassen eingefügt werden. In Abbildung 10-13 wird das Einschleusen von featureflags gezeigt

```csharp
public class ProductController : Controller
{
    private readonly IFeatureManager _featureManager;

    public ProductController(IFeatureManager featureManager)
    {
        _featureManager = featureManager;
    }
}
```

**Abbildung 10-13** : Einschleusen von featureflags in eine Klasse.

Mit den featureverwaltungsbibliotheken wird der Lebenszyklus von featureflags im Hintergrund verwaltet. Um z. b. eine große Anzahl von Aufrufen des Konfigurations Speichers zu minimieren, werden die Status der Bibliotheken für eine angegebene Dauer von den Bibliotheken zwischengespeichert. Sie können die Unveränderlichkeit von flagzuständen während eines Anforderungs Aufrufes gewährleisten. Sie bieten auch einen `Point-in-time snapshot` . Sie können den Verlauf eines beliebigen Schlüssel Werts wiederherstellen und seinen bisherigen Wert in einem beliebigen Moment innerhalb der letzten sieben Tage angeben.

>[!div class="step-by-step"]
>[Zurück](devops.md)
>[Weiter](infrastructure-as-code.md)
