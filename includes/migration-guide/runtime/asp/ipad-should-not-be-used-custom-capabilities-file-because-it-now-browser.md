---
ms.openlocfilehash: 84f570cbbd97be79426e117d4c97ec182a397fd4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235541"
---
### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a><span data-ttu-id="7778a-101">„iPad“ sollte in der Datei für benutzerdefinierte Funktionen nicht verwendet werden, da es sich dabei nun um eine Browserfunktion handelt</span><span class="sxs-lookup"><span data-stu-id="7778a-101">IPad should not be used in custom capabilities file because it is now a browser capability</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7778a-102">Details</span><span class="sxs-lookup"><span data-stu-id="7778a-102">Details</span></span>|<span data-ttu-id="7778a-103">Ab .NET Framework 4.5 handelt es sich bei „iPad“ um einen Bezeichner in der ASP.NET-Standarddatei für Browserfunktionen, der deshalb nicht in einer Datei für benutzerdefinierte Funktionen verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="7778a-103">Beginning in .NET Framework 4.5, iPad is an identifier in the default ASP.NET browser capabilities file, so it should not be used in a custom capabilities file</span></span>|
|<span data-ttu-id="7778a-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="7778a-104">Suggestion</span></span>|<span data-ttu-id="7778a-105">Wenn bestimmte Funktionen von „iPad“ erforderlich sind, muss das Verhalten von „iPad“ geändert werden, indem die Funktionen auf dem vorab definierten Gateway auf „refID &quot;iPad&quot;“ festgelegt werden, statt eine neue ID für &quot;iPad&quot; durch Abgleich mit dem Benutzer-Agent zu generieren.</span><span class="sxs-lookup"><span data-stu-id="7778a-105">If iPad-specific capabilities are required, it is necessary to modify iPad behavior by setting capabilities on the pre-defined gateway refID &quot;IPad&quot; instead of by generating a new &quot;IPad&quot; ID by user agent matching.</span></span>|
|<span data-ttu-id="7778a-106">Bereich</span><span class="sxs-lookup"><span data-stu-id="7778a-106">Scope</span></span>|<span data-ttu-id="7778a-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7778a-107">Edge</span></span>|
|<span data-ttu-id="7778a-108">Version</span><span class="sxs-lookup"><span data-stu-id="7778a-108">Version</span></span>|<span data-ttu-id="7778a-109">4.5</span><span class="sxs-lookup"><span data-stu-id="7778a-109">4.5</span></span>|
|<span data-ttu-id="7778a-110">Typ</span><span class="sxs-lookup"><span data-stu-id="7778a-110">Type</span></span>|<span data-ttu-id="7778a-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="7778a-111">Runtime</span></span>|
