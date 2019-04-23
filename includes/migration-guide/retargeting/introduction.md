---
ms.openlocfilehash: d4f22aa41eb7aeffd655d980cb8418649462273e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757757"
---
## <a name="introduction"></a><span data-ttu-id="b0e38-101">Einführung</span><span class="sxs-lookup"><span data-stu-id="b0e38-101">Introduction</span></span>
<span data-ttu-id="b0e38-102">Neuzuweisungsänderungen wirken sich auf Apps aus, die für eine andere .NET Framework-Instanz neu kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="b0e38-102">Retargeting changes affect apps that are recompiled to target a different .NET Framework.</span></span> <span data-ttu-id="b0e38-103">Dazu zählen:</span><span class="sxs-lookup"><span data-stu-id="b0e38-103">They include:</span></span>

* <span data-ttu-id="b0e38-104">Änderungen in der Entwurfszeitumgebung.</span><span class="sxs-lookup"><span data-stu-id="b0e38-104">Changes in the design-time environment.</span></span> <span data-ttu-id="b0e38-105">Beispielsweise können Buildtools Warnungen ausgeben, obwohl dies zuvor nicht der Fall war.</span><span class="sxs-lookup"><span data-stu-id="b0e38-105">For example, build tools may emit warnings when previously they did not.</span></span>

* <span data-ttu-id="b0e38-106">Änderungen in der Laufzeitumgebung.</span><span class="sxs-lookup"><span data-stu-id="b0e38-106">Changes in the runtime environment.</span></span> <span data-ttu-id="b0e38-107">Dies betrifft nur Apps, die speziell diese .NET Framework-Instanz als Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0e38-107">These affect only apps that specifically target the retargeted .NET Framework.</span></span> <span data-ttu-id="b0e38-108">Apps, die auf frühere Versionen von .NET Framework abzielen, verhalten sich so, als würden sie in diesen Versionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b0e38-108">Apps that target previous versions of the .NET Framework behave as they did when running under those versions.</span></span>

<span data-ttu-id="b0e38-109">In den Artikeln, in denen Neuzuweisungsänderungen beschrieben werden, haben wir die einzelnen Punkte entsprechend ihrer erwarteten Auswirkung eingestuft:</span><span class="sxs-lookup"><span data-stu-id="b0e38-109">In the topics that describe retargeting changes, we have classified individual items by their expected impact, as follows:</span></span>

<span data-ttu-id="b0e38-110">**Größer** Dies ist eine wesentliche Änderung, die viele Apps beeinträchtigt oder erhebliche Änderungen des Codes erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="b0e38-110">**Major** This is a significant change that affects a large number of apps or that requires substantial modification of code.</span></span>

<span data-ttu-id="b0e38-111">**Kleiner** Dies ist eine Änderung, die eine kleine Anzahl von Apps beeinträchtigt oder geringfügige Änderungen des Codes erforderlich macht.</span><span class="sxs-lookup"><span data-stu-id="b0e38-111">**Minor** This is a change that affects a small number of apps or that requires minor modification of code.</span></span>

<span data-ttu-id="b0e38-112">**Grenzfall** Diese Änderung beeinträchtigt Apps nur in sehr spezifischen Szenarien, die nicht häufig vorkommen.</span><span class="sxs-lookup"><span data-stu-id="b0e38-112">**Edge case** This is a change that affects apps under very specific scenarios that are not common.</span></span>

<span data-ttu-id="b0e38-113">**Transparent** Diese Änderung hat keine nennenswerten Auswirkungen, die Entwickler oder Benutzer beachten müssten.</span><span class="sxs-lookup"><span data-stu-id="b0e38-113">**Transparent** This is a change that has no noticeable effect on the app's developer or user.</span></span> <span data-ttu-id="b0e38-114">Die App sollte keine Änderung benötigen.</span><span class="sxs-lookup"><span data-stu-id="b0e38-114">The app should not require modification because of this change.</span></span>
