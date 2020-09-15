---
ms.openlocfilehash: f78d15338aa49de5b729aca12964924a0df00ec6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614547"
---
### <a name="improved-accessibility-for-some-net-sdk-tools"></a><span data-ttu-id="6a441-101">Verbesserte Barrierefreiheit für einige .NET SDK-Tools</span><span class="sxs-lookup"><span data-stu-id="6a441-101">Improved accessibility for some .NET SDK tools</span></span>

#### <a name="details"></a><span data-ttu-id="6a441-102">Details</span><span class="sxs-lookup"><span data-stu-id="6a441-102">Details</span></span>

<span data-ttu-id="6a441-103">Im .NET Framework SDK 4.7.1 wurden die Tools „SvcConfigEditor.exe“ und „SvcTraceViewer.exe“ verbessert, indem verschiedene Probleme mit der Barrierefreiheit behoben wurden.</span><span class="sxs-lookup"><span data-stu-id="6a441-103">In the .NET Framework SDK 4.7.1, the SvcConfigEditor.exe and SvcTraceViewer.exe tools have been improved by fixing varied accessibility issues.</span></span> <span data-ttu-id="6a441-104">Bei den meisten handelte es sich um kleinere Probleme, durch die ein Name nicht definiert wurde oder bestimmte Muster für die Benutzeroberflächenautomatisierung nicht richtig implementiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6a441-104">Most of these were small issues like a name not being defined or certain UI automation patterns not being implemented correctly.</span></span> <span data-ttu-id="6a441-105">Obwohl viele Benutzer diese falschen Werte nicht bemerken würden, erhöhen die SDK-Tools die Benutzerfreundlichkeit für Kunden, die Hilfstechnologien wie die Sprachausgabe verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a441-105">While many users wouldn't be aware of these incorrect values, customers who use assistive technologies like screen readers will find these SDK tools more accessible.</span></span> <span data-ttu-id="6a441-106">Diese Problembehebungen ändern vorherige Verhalten wie z.B. die Tastaturfokusreihenfolge. Sie können der Datei „app.config“ Folgendes hinzufügen, um alle Problembehebungen für die Barrierefreiheit in diesen Tools nutzen zu können:</span><span class="sxs-lookup"><span data-stu-id="6a441-106">Certainly, these fixes change some previous behaviors, like keyboard focus order.In order to get all the accessibility fixes in these tools, you can the following to your app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false"/>
</runtime>
```

| <span data-ttu-id="6a441-107">name</span><span class="sxs-lookup"><span data-stu-id="6a441-107">Name</span></span>    | <span data-ttu-id="6a441-108">Wert</span><span class="sxs-lookup"><span data-stu-id="6a441-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6a441-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="6a441-109">Scope</span></span>   | <span data-ttu-id="6a441-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6a441-110">Edge</span></span>        |
| <span data-ttu-id="6a441-111">Version</span><span class="sxs-lookup"><span data-stu-id="6a441-111">Version</span></span> | <span data-ttu-id="6a441-112">4.7.1</span><span class="sxs-lookup"><span data-stu-id="6a441-112">4.7.1</span></span>       |
| <span data-ttu-id="6a441-113">Typ</span><span class="sxs-lookup"><span data-stu-id="6a441-113">Type</span></span>    | <span data-ttu-id="6a441-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="6a441-114">Retargeting</span></span> |
