---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235565"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="2117a-101">Die CheckForOverflowUnderflow-Eigenschaft von WinForm ist jetzt für System.Drawing auf TRUE festgelegt</span><span class="sxs-lookup"><span data-stu-id="2117a-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2117a-102">Details</span><span class="sxs-lookup"><span data-stu-id="2117a-102">Details</span></span>|<span data-ttu-id="2117a-103">Die CheckForOverflowUnderflow-Eigenschaft für die Assembly „System.Drawing.dll“ ist auf TRUE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2117a-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>|
|<span data-ttu-id="2117a-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2117a-104">Suggestion</span></span>|<span data-ttu-id="2117a-105">Zuvor wurde das Ergebnis im Fall von Überläufen automatisch abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="2117a-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="2117a-106">Nun wird eine <xref:System.OverflowException?displayProperty=name>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="2117a-106">Now an <xref:System.OverflowException?displayProperty=name> exception is thrown.</span></span>|
|<span data-ttu-id="2117a-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="2117a-107">Scope</span></span>|<span data-ttu-id="2117a-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2117a-108">Edge</span></span>|
|<span data-ttu-id="2117a-109">Version</span><span class="sxs-lookup"><span data-stu-id="2117a-109">Version</span></span>|<span data-ttu-id="2117a-110">4.5</span><span class="sxs-lookup"><span data-stu-id="2117a-110">4.5</span></span>|
|<span data-ttu-id="2117a-111">Typ</span><span class="sxs-lookup"><span data-stu-id="2117a-111">Type</span></span>|<span data-ttu-id="2117a-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2117a-112">Runtime</span></span>|
