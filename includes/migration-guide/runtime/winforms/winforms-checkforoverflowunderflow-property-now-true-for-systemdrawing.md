---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379671"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="2b45b-101">Die CheckForOverflowUnderflow-Eigenschaft von WinForm ist jetzt für System.Drawing auf TRUE festgelegt</span><span class="sxs-lookup"><span data-stu-id="2b45b-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2b45b-102">Details</span><span class="sxs-lookup"><span data-stu-id="2b45b-102">Details</span></span>|<span data-ttu-id="2b45b-103">Die CheckForOverflowUnderflow-Eigenschaft für die Assembly „System.Drawing.dll“ ist auf TRUE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2b45b-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>|
|<span data-ttu-id="2b45b-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2b45b-104">Suggestion</span></span>|<span data-ttu-id="2b45b-105">Zuvor wurde das Ergebnis im Fall von Überläufen automatisch abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="2b45b-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="2b45b-106">Nun wird eine <xref:System.OverflowException?displayProperty=name>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="2b45b-106">Now an <xref:System.OverflowException?displayProperty=name> exception is thrown.</span></span>|
|<span data-ttu-id="2b45b-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="2b45b-107">Scope</span></span>|<span data-ttu-id="2b45b-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2b45b-108">Edge</span></span>|
|<span data-ttu-id="2b45b-109">Version</span><span class="sxs-lookup"><span data-stu-id="2b45b-109">Version</span></span>|<span data-ttu-id="2b45b-110">4.5</span><span class="sxs-lookup"><span data-stu-id="2b45b-110">4.5</span></span>|
|<span data-ttu-id="2b45b-111">Typ</span><span class="sxs-lookup"><span data-stu-id="2b45b-111">Type</span></span>|<span data-ttu-id="2b45b-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2b45b-112">Runtime</span></span>|
