---
ms.openlocfilehash: f980c8029375074889505a8eb7e8a65aaa8d74e4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614519"
---
### <a name="resgen-refuses-to-load-content-from-the-web"></a><span data-ttu-id="2b2b3-101">Resgen lehnt das Laden von Inhalten aus dem Web ab</span><span class="sxs-lookup"><span data-stu-id="2b2b3-101">Resgen refuses to load content from the web</span></span>

#### <a name="details"></a><span data-ttu-id="2b2b3-102">Details</span><span class="sxs-lookup"><span data-stu-id="2b2b3-102">Details</span></span>

<span data-ttu-id="2b2b3-103">RESX-Dateien können binär formatierte Eingaben enthalten.</span><span class="sxs-lookup"><span data-stu-id="2b2b3-103">.resx files may contain binary formatted input.</span></span> <span data-ttu-id="2b2b3-104">Wenn Sie versuchen, mit Resgen eine Datei zu laden, die aus einem nicht vertrauenswürdigen Speicherort heruntergeladen wurde, schlägt das Laden der Eingabe standardmäßig fehl.</span><span class="sxs-lookup"><span data-stu-id="2b2b3-104">If you attempt to use resgen to load a file that was downloaded from an untrusted location, it will fail to load the input by default.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2b2b3-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="2b2b3-105">Suggestion</span></span>

<span data-ttu-id="2b2b3-106">Benutzer von Resgen, die binär formatierte Eingaben aus nicht vertrauenswürdigen Speicherorten laden müssen, können entweder die Markierung des Webs aus der Eingabedatei entfernen oder die Deaktivierungsmethode anwenden.Fügen Sie die folgende Registrierungseinstellung hinzu, um die computerweite Deaktivierungsmethode anzuwenden: [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;</span><span class="sxs-lookup"><span data-stu-id="2b2b3-106">Resgen users who require loading binary formatted input from untrusted locations can either remove the mark of the web from the input file or apply the opt-out quirk.Add the following registry setting to apply the machine wide opt-out quirk: [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft.NETFramework\SDK] &quot;AllowProcessOfUntrustedResourceFiles&quot;=&quot;true&quot;</span></span>

| <span data-ttu-id="2b2b3-107">name</span><span class="sxs-lookup"><span data-stu-id="2b2b3-107">Name</span></span>    | <span data-ttu-id="2b2b3-108">Wert</span><span class="sxs-lookup"><span data-stu-id="2b2b3-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2b2b3-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="2b2b3-109">Scope</span></span>   | <span data-ttu-id="2b2b3-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2b2b3-110">Edge</span></span>        |
| <span data-ttu-id="2b2b3-111">Version</span><span class="sxs-lookup"><span data-stu-id="2b2b3-111">Version</span></span> | <span data-ttu-id="2b2b3-112">4.7.2</span><span class="sxs-lookup"><span data-stu-id="2b2b3-112">4.7.2</span></span>       |
| <span data-ttu-id="2b2b3-113">Typ</span><span class="sxs-lookup"><span data-stu-id="2b2b3-113">Type</span></span>    | <span data-ttu-id="2b2b3-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="2b2b3-114">Retargeting</span></span> |
