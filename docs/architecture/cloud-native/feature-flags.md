---
title: Featureflags
description: Implementieren von featureflags in Cloud-native Anwendungen mit Azure-app config
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: be4ab307069065975dc22d6bd984e12a2ea1457d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540464"
---
# <a name="feature-flags"></a><span data-ttu-id="9ef1f-103">Featureflags</span><span class="sxs-lookup"><span data-stu-id="9ef1f-103">Feature flags</span></span>

<span data-ttu-id="9ef1f-104">In Kapitel 1 haben wir bestätigt, dass Cloud Native sehr viel über Geschwindigkeit und Agilität verfügt.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-104">In chapter 1, we affirmed that cloud native is much about speed and agility.</span></span> <span data-ttu-id="9ef1f-105">Benutzer erwarten schnelle Reaktionsfähigkeit, innovative Features und keine Ausfallzeiten.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-105">Users expect rapid responsiveness, innovative features, and zero downtime.</span></span> <span data-ttu-id="9ef1f-106">`Feature flags` bei handelt es sich um ein modernes Bereitstellungs Verfahren, mit dem sich die Agilität von cloudbasierten Anwendungen erhöhen lässt</span><span class="sxs-lookup"><span data-stu-id="9ef1f-106">`Feature flags` are a modern deployment technique that helps increase agility for cloud-native applications.</span></span> <span data-ttu-id="9ef1f-107">Sie ermöglichen es Ihnen, neue Features in einer Produktionsumgebung bereitzustellen, aber die Verfügbarkeit einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-107">They enable you to deploy new features into a production environment, but restrict their availability.</span></span> <span data-ttu-id="9ef1f-108">Mit der flicke eines Schalters können Sie ein neues Feature für bestimmte Benutzer aktivieren, ohne die APP neu zu starten oder neuen Code bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-108">With the flick of a switch, you can activate a new feature for specific users without restarting the app or deploying new code.</span></span> <span data-ttu-id="9ef1f-109">Sie trennen die Freigabe neuer Features von ihrer Code Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-109">They separate the release of new features from their code deployment.</span></span>

<span data-ttu-id="9ef1f-110">Merkmals Flags basieren auf einer bedingten Logik, die die Sichtbarkeit von Benutzern zur Laufzeit steuert.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-110">Feature flags are built upon conditional logic that control visibility of functionality for users at runtime.</span></span> <span data-ttu-id="9ef1f-111">In modernen, cloudbasierten Systemen ist es üblich, neue Features frühzeitig in der Produktion bereitzustellen, Sie aber mit einer begrenzten Zielgruppe zu testen.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-111">In modern cloud-native systems, it's common to deploy new features into production early, but test them with a limited audience.</span></span> <span data-ttu-id="9ef1f-112">Wenn das Vertrauen zunimmt, kann die Funktion inkrementell für größere Zielgruppen eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-112">As confidence increases, the feature can be incrementally rolled out to wider audiences.</span></span>

<span data-ttu-id="9ef1f-113">Weitere Anwendungsfälle für Merkmals Flags sind:</span><span class="sxs-lookup"><span data-stu-id="9ef1f-113">Other use cases for feature flags include:</span></span>

- <span data-ttu-id="9ef1f-114">Beschränken Sie die Premium-Funktionalität auf bestimmte Kundengruppen, die zur Zahlung höherer Abonnementgebühren bereit sind.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-114">Restrict premium functionality to specific customer groups willing to pay higher subscription fees.</span></span>
- <span data-ttu-id="9ef1f-115">Stabilisieren Sie ein System, indem Sie eine Problem Funktion schnell deaktivieren und so die Risiken eines Rollbacks oder sofortigen Hotfixes vermeiden.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-115">Stabilize a system by quickly deactivating a problem feature, avoiding the risks of a rollback or immediate hotfix.</span></span>
- <span data-ttu-id="9ef1f-116">Deaktivieren Sie ein optionales Feature mit hohem Ressourcenverbrauch während der Spitzenzeiten.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-116">Disable an optional feature with high resource consumption during peak usage periods.</span></span>
- <span data-ttu-id="9ef1f-117">Durchführen `experimental feature releases` von kleinen Benutzer Segmenten zum Überprüfen der Durchführbarkeit und Beliebtheit</span><span class="sxs-lookup"><span data-stu-id="9ef1f-117">Conduct `experimental feature releases` to small user segments to validate feasibility and popularity.</span></span>

<span data-ttu-id="9ef1f-118">Merkmals Flags fördern auch die `trunk-based` Entwicklung.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-118">Feature flags also promote `trunk-based` development.</span></span> <span data-ttu-id="9ef1f-119">Dabei handelt es sich um ein Branchen Modell zur Quell Code Verwaltung, in dem Entwickler an Features in einer einzelnen Verzweigung zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-119">It's a source-control branching model where developers collaborate on features in a single branch.</span></span> <span data-ttu-id="9ef1f-120">Der Ansatz minimiert das Risiko und die Komplexität der Zusammenführung einer großen Anzahl von featurebranches mit langer Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-120">The approach minimizes the risk and complexity of merging large numbers of long-running feature branches.</span></span> <span data-ttu-id="9ef1f-121">Die Funktionen sind bis zur Aktivierung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-121">Features are unavailable until activated.</span></span>

## <a name="implementing-feature-flags"></a><span data-ttu-id="9ef1f-122">Implementieren von featureflags</span><span class="sxs-lookup"><span data-stu-id="9ef1f-122">Implementing feature flags</span></span>

<span data-ttu-id="9ef1f-123">Im Kern ist ein Merkmals Flag ein Verweis auf einen einfachen `decision object` .</span><span class="sxs-lookup"><span data-stu-id="9ef1f-123">At its core, a feature flag is a reference to a simple `decision object`.</span></span> <span data-ttu-id="9ef1f-124">Sie gibt einen booleschen Zustand von `on` oder zurück `off` .</span><span class="sxs-lookup"><span data-stu-id="9ef1f-124">It returns a Boolean state of `on` or `off`.</span></span> <span data-ttu-id="9ef1f-125">Das Flag umschließt in der Regel einen Codeblock, der eine featurefunktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-125">The flag typically wraps a block of code that encapsulates a feature capability.</span></span> <span data-ttu-id="9ef1f-126">Der Status des Flags bestimmt, ob dieser Codeblock für einen bestimmten Benutzer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-126">The state of the flag determines whether that code block executes for a given user.</span></span> <span data-ttu-id="9ef1f-127">In Abbildung 10-11 wird die Implementierung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-127">Figure 10-11 shows the implementation.</span></span>

```csharp
if (featureFlag) {
    // Run this code block if the featureFlag value is true
} else {
    // Run this code block if the featureFlag value is false
}
```

<span data-ttu-id="9ef1f-128">**Abbildung 10-11** -einfache Implementierung von featureflags.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-128">**Figure 10-11** - Simple feature flag implementation.</span></span>

<span data-ttu-id="9ef1f-129">Beachten Sie, dass diese Vorgehensweise die Entscheidungs Logik von dem Funktionscode trennt.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-129">Note how this approach separates the decision logic from the feature code.</span></span>

<span data-ttu-id="9ef1f-130">In Kapitel 1 wurde erläutert `Twelve-Factor App` .</span><span class="sxs-lookup"><span data-stu-id="9ef1f-130">In chapter 1, we discussed the `Twelve-Factor App`.</span></span> <span data-ttu-id="9ef1f-131">Es wird empfohlen, Konfigurationseinstellungen Extern aus dem ausführbaren Code der Anwendung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-131">The guidance recommended keeping configuration settings external from application executable code.</span></span> <span data-ttu-id="9ef1f-132">Bei Bedarf können die Einstellungen aus der externen Quelle gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-132">When needed, settings can be read in from the external source.</span></span> <span data-ttu-id="9ef1f-133">Merkmals Flag-Konfigurationswerte sollten auch unabhängig von Ihrer Codebasis sein.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-133">Feature flag configuration values should also be independent from their codebase.</span></span> <span data-ttu-id="9ef1f-134">Durch externalisieren der Flag-Konfiguration in einem separaten Repository können Sie den Flag-Status ändern, ohne die Anwendung zu ändern und erneut bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-134">By externalizing flag configuration in a separate repository, you can change flag state without modifying and redeploying the application.</span></span>

<span data-ttu-id="9ef1f-135">[Azure-App Konfiguration](https://docs.microsoft.com/azure/azure-app-configuration/overview) stellt ein zentralisiertes Repository für Merkmals Flags bereit.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-135">[Azure App Configuration](https://docs.microsoft.com/azure/azure-app-configuration/overview) provides a centralized repository for feature flags.</span></span> <span data-ttu-id="9ef1f-136">Mit dieser Funktion definieren Sie verschiedene Arten von featureflags und ändern ihre Zustände schnell und zuverlässig.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-136">With it, you define different kinds of feature flags and manipulate their states quickly and confidently.</span></span> <span data-ttu-id="9ef1f-137">Sie fügen der Anwendung die Client Bibliotheken für die APP-Konfiguration hinzu, um Feature-Flag-Funktionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-137">You add the App Configuration client libraries to your application to enable feature flag functionality.</span></span> <span data-ttu-id="9ef1f-138">Verschiedene Frameworks für Programmiersprachen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-138">Various programming language frameworks are supported.</span></span>

<span data-ttu-id="9ef1f-139">Merkmals Flags können problemlos in einem [ASP.net Core-Dienst](https://docs.microsoft.com/azure/azure-app-configuration/use-feature-flags-dotnet-core)implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-139">Feature flags can be easily implemented in an [ASP.NET Core service](https://docs.microsoft.com/azure/azure-app-configuration/use-feature-flags-dotnet-core).</span></span> <span data-ttu-id="9ef1f-140">Durch die Installation der .net-funktionsverwaltungs-Bibliotheken und des App-Konfigurations Anbieters können Sie Ihrem Code deklarativ Merkmals Flags hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-140">Installing the .NET Feature Management libraries and App Configuration provider enable you to declaratively add feature flags to your code.</span></span> <span data-ttu-id="9ef1f-141">Sie aktivieren `FeatureGate` Attribute, sodass Sie nicht manuell if-Anweisungen in Ihre CodeBase schreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-141">They enable `FeatureGate` attributes so that you don't have to manually write if statements across your codebase.</span></span>

<span data-ttu-id="9ef1f-142">Nachdem Sie in der Startup-Klasse konfiguriert wurde, können Sie Feature-Flag-Funktionalität auf Controller-, Aktions-oder Middleware-Ebene hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-142">Once configured in your Startup class, you can add feature flag functionality at the controller, action, or middleware level.</span></span> <span data-ttu-id="9ef1f-143">In Abbildung 10-12 wird die Implementierung von Controller und Aktion dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9ef1f-143">Figure 10-12 presents controller and action implementation:</span></span>

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

<span data-ttu-id="9ef1f-144">**Abbildung 10-12** : Implementierung von featureflags in einem Controller und einer Aktion.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-144">**Figure 10-12** - Feature flag implementation in a controller and action.</span></span>

<span data-ttu-id="9ef1f-145">Wenn ein Merkmals Flag deaktiviert ist, empfängt der Benutzer den Statuscode 404 (nicht gefunden) ohne Antworttext.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-145">If a feature flag is disabled, the user will receive a 404 (Not Found) status code with no response body.</span></span>

<span data-ttu-id="9ef1f-146">Merkmals Flags können auch direkt in c#-Klassen eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-146">Feature flags can also be injected directly into C# classes.</span></span> <span data-ttu-id="9ef1f-147">In Abbildung 10-13 wird das Einschleusen von featureflags gezeigt</span><span class="sxs-lookup"><span data-stu-id="9ef1f-147">Figure 10-13 shows feature flag injection:</span></span>

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

<span data-ttu-id="9ef1f-148">**Abbildung 10-13** : Einschleusen von featureflags in eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-148">**Figure 10-13** - Feature flag injection into a class.</span></span>

<span data-ttu-id="9ef1f-149">Mit den featureverwaltungsbibliotheken wird der Lebenszyklus von featureflags im Hintergrund verwaltet.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-149">The Feature Management libraries manage the feature flag lifecycle behind the scenes.</span></span> <span data-ttu-id="9ef1f-150">Um z. b. eine große Anzahl von Aufrufen des Konfigurations Speichers zu minimieren, werden die Status der Bibliotheken für eine angegebene Dauer von den Bibliotheken zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-150">For example, to minimize high numbers of calls to the configuration store, the libraries cache flag states for a specified duration.</span></span> <span data-ttu-id="9ef1f-151">Sie können die Unveränderlichkeit von flagzuständen während eines Anforderungs Aufrufes gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-151">They can guarantee the immutability of flag states during a request call.</span></span> <span data-ttu-id="9ef1f-152">Sie bieten auch einen `Point-in-time snapshot` .</span><span class="sxs-lookup"><span data-stu-id="9ef1f-152">They also offer a `Point-in-time snapshot`.</span></span> <span data-ttu-id="9ef1f-153">Sie können den Verlauf eines beliebigen Schlüssel Werts wiederherstellen und seinen bisherigen Wert in einem beliebigen Moment innerhalb der letzten sieben Tage angeben.</span><span class="sxs-lookup"><span data-stu-id="9ef1f-153">You can reconstruct the history of any key-value and provide its past value at any moment within the previous seven days.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9ef1f-154">[Zurück](devops.md)
>[Weiter](infrastructure-as-code.md)</span><span class="sxs-lookup"><span data-stu-id="9ef1f-154">[Previous](devops.md)
[Next](infrastructure-as-code.md)</span></span>
