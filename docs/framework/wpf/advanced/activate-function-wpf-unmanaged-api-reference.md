---
title: Aktivieren der Funktion-WPF-Referenz zur nicht verwalteten API
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 9c0a235e8b94294ab82da88e43f7446c29739c12
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734509"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="d379e-102">Funktion aktivieren (Referenz zur nicht verwalteten WPF-API)</span><span class="sxs-lookup"><span data-stu-id="d379e-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="d379e-103">Diese API unterstützt die Windows Presentation Foundation-Infrastruktur (WPF) und ist nicht für die direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="d379e-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="d379e-104">Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Windows-Verwaltung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d379e-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="d379e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d379e-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="d379e-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="d379e-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="d379e-107">Ein Zeiger auf die Aktivierungs Parameter des Fensters.</span><span class="sxs-lookup"><span data-stu-id="d379e-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="d379e-108">Ein Zeiger auf die Adresse eines Einzelelement Puffers, der einen Zeiger auf ein <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="d379e-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="d379e-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d379e-109">Requirements</span></span>

<span data-ttu-id="d379e-110">**Plattformen:** Siehe [.NET Framework System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d379e-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d379e-111">**DLL**</span><span class="sxs-lookup"><span data-stu-id="d379e-111">**DLL:**</span></span>

<span data-ttu-id="d379e-112">In den .NET Framework 3,0 und 3,5: presentationhostdll. dll</span><span class="sxs-lookup"><span data-stu-id="d379e-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="d379e-113">In den .NET Framework 4 und höher: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="d379e-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="d379e-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d379e-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d379e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d379e-115">See also</span></span>

- [<span data-ttu-id="d379e-116">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="d379e-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
