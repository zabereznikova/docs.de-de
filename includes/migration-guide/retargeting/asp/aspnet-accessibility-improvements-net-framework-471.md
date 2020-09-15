---
ms.openlocfilehash: 418bcdca1e9a325894891d7b0e080ce035e2d1b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614458"
---
### <a name="aspnet-accessibility-improvements-in-net-framework-471"></a><span data-ttu-id="aff43-101">Verbesserungen der Barrierefreiheit von ASP.NET in .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="aff43-101">ASP.NET Accessibility Improvements in .NET Framework 4.7.1</span></span>

#### <a name="details"></a><span data-ttu-id="aff43-102">Details</span><span class="sxs-lookup"><span data-stu-id="aff43-102">Details</span></span>

<span data-ttu-id="aff43-103">Ab .NET Framework 4.7.1 arbeiten .ASP.NET-Websteuerelemente effizienter mit den Funktionen für die Barrierefreiheit in Visual Studio zusammen, wodurch ASP.NET-Kunden besser unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="aff43-103">Starting with the .NET Framework 4.7.1, ASP.NET has improved how ASP.NET Web Controls work with accessibility technology in Visual Studio to better support ASP.NET customers.</span></span>  <span data-ttu-id="aff43-104">Folgende Änderungen wurden u.a. vorgenommen:</span><span class="sxs-lookup"><span data-stu-id="aff43-104">These include the following changes:</span></span>

- <span data-ttu-id="aff43-105">Änderungen, durch die fehlende Barrierefreiheitsmuster für Steuerelemente der Benutzeroberfläche implementiert werden. Zu diesen Steuerelementen zählen z.B. das Dialogfeld „Feld hinzufügen“ im Detailansicht-Assistenten oder das Dialogfeld „ListView konfigurieren“ im ListView-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="aff43-105">Changes to implement missing UI accessibility patterns in controls, like the Add Field dialog in the Details View wizard, or the Configure ListView dialog of the ListView wizard.</span></span>
- <span data-ttu-id="aff43-106">Änderungen zur Verbesserung der Anzeige im Modus für hohe Kontraste, z.B. beim DataPager-Feld-Editor.</span><span class="sxs-lookup"><span data-stu-id="aff43-106">Changes to improve the display in High Contrast mode, like the Data Pager Fields Editor.</span></span>
- <span data-ttu-id="aff43-107">Änderungen zur Verbesserung der Benutzerfreundlichkeit bei der Tastaturnavigation für Steuerelemente, z.B. beim Dialogfeld „Felder“ im Assistenten für das Bearbeiten von Pagerfeldern des DataPager-Steuerelements, beim Dialogfeld „ObjectContext konfigurieren“ oder beim Dialogfeld „Datenauswahl konfigurieren“ des Assistenten zum Konfigurieren der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="aff43-107">Changes to improve the keyboard navigation experiences for controls, like the Fields dialog in the Edit Pager Fields wizard of the DataPager control, the Configure ObjectContext dialog, or the Configure Data Selection dialog of the Configure Data Source wizard.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="aff43-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="aff43-108">Suggestion</span></span>

<span data-ttu-id="aff43-109">**Aktivieren oder Deaktivieren dieser Änderungen:** Damit diese Änderungen in Visual Studio Designer eingesetzt werden können, muss das Tool unter .NET Framework 4.7.1 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="aff43-109">**How to opt in or out of these changes** In order for the Visual Studio Designer to benefit from these changes, it must run on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="aff43-110">Die Webanwendung kann diese Änderungen nutzen, wenn Sie folgende Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="aff43-110">The web application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="aff43-111">Installieren Sie Visual Studio 2017 15.3 oder höher. Ab dieser Version werden die neuen Barrierefreiheitsfeatures mit der unten aufgeführten AppContext-Option standardmäßig unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aff43-111">Install Visual Studio 2017 15.3 or later, which supports the new accessibility features with the following AppContext Switch by default.</span></span>
- <span data-ttu-id="aff43-112">Deaktivieren Sie die Legacy-Barrierefreiheitsverhalten, indem Sie in der Konfigurationsdatei „devenv.exe“ dem Abschnitt `<runtime>` die AppContext-Option `Switch.UseLegacyAccessibilityFeatures` hinzufügen und sie auf `false` festlegen, wie im folgenden Beispiel dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="aff43-112">Opt out of the legacy accessibility behaviors by adding the `Switch.UseLegacyAccessibilityFeatures` AppContext switch to the `<runtime>` section in the devenv.exe.config file and setting it to `false`, as the following example shows.</span></span>

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

<span data-ttu-id="aff43-113">Bei Anwendungen, die .NET Framework 4.7.1 oder höher als Zielplattform verwenden und die Legacy-Barrierefreiheitsverhalten beibehalten sollen, können Sie die Verwendung des veralteten Features für die Barrierefreiheit aktivieren, indem Sie die AppContext-Option auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="aff43-113">Applications that target the .NET Framework 4.7.1 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="aff43-114">name</span><span class="sxs-lookup"><span data-stu-id="aff43-114">Name</span></span>    | <span data-ttu-id="aff43-115">Wert</span><span class="sxs-lookup"><span data-stu-id="aff43-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="aff43-116">Bereich</span><span class="sxs-lookup"><span data-stu-id="aff43-116">Scope</span></span>   | <span data-ttu-id="aff43-117">Gering</span><span class="sxs-lookup"><span data-stu-id="aff43-117">Minor</span></span>       |
| <span data-ttu-id="aff43-118">Version</span><span class="sxs-lookup"><span data-stu-id="aff43-118">Version</span></span> | <span data-ttu-id="aff43-119">4.7.1</span><span class="sxs-lookup"><span data-stu-id="aff43-119">4.7.1</span></span>       |
| <span data-ttu-id="aff43-120">Typ</span><span class="sxs-lookup"><span data-stu-id="aff43-120">Type</span></span>    | <span data-ttu-id="aff43-121">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="aff43-121">Retargeting</span></span> |
