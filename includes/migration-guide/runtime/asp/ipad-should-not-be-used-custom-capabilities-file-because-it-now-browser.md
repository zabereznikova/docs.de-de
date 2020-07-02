---
ms.openlocfilehash: af10716fe5f4c07091e8605cdf620e4a499fb1e8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620178"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="5f763-101">„iPad“ sollte in der Datei für benutzerdefinierte Funktionen nicht verwendet werden, da es sich dabei nun um eine Browserfunktion handelt</span><span class="sxs-lookup"><span data-stu-id="5f763-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

#### <a name="details"></a><span data-ttu-id="5f763-102">Details</span><span class="sxs-lookup"><span data-stu-id="5f763-102">Details</span></span>

<span data-ttu-id="5f763-103">Ab .NET Framework 4.5 handelt es sich bei „iPad“ um einen Bezeichner in der ASP.NET-Standarddatei für Browserfunktionen, der deshalb nicht in einer Datei für benutzerdefinierte Funktionen verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="5f763-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5f763-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="5f763-104">Suggestion</span></span>

<span data-ttu-id="5f763-105">Wenn bestimmte Funktionen von „iPad“ erforderlich sind, muss das Verhalten von „iPad“ geändert werden, indem die Funktionen auf dem vorab definierten Gateway auf „refID &quot;iPad&quot;“ festgelegt werden, statt eine neue ID für &quot;iPad&quot; durch Abgleich mit dem Benutzer-Agent zu generieren.</span><span class="sxs-lookup"><span data-stu-id="5f763-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>

| <span data-ttu-id="5f763-106">name</span><span class="sxs-lookup"><span data-stu-id="5f763-106">Name</span></span>    | <span data-ttu-id="5f763-107">Wert</span><span class="sxs-lookup"><span data-stu-id="5f763-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5f763-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="5f763-108">Scope</span></span>   |<span data-ttu-id="5f763-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5f763-109">Edge</span></span>|
|<span data-ttu-id="5f763-110">Version</span><span class="sxs-lookup"><span data-stu-id="5f763-110">Version</span></span>|<span data-ttu-id="5f763-111">4.5</span><span class="sxs-lookup"><span data-stu-id="5f763-111">4.5</span></span>|
|<span data-ttu-id="5f763-112">Typ</span><span class="sxs-lookup"><span data-stu-id="5f763-112">Type</span></span>|<span data-ttu-id="5f763-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="5f763-113">Runtime</span></span>|
