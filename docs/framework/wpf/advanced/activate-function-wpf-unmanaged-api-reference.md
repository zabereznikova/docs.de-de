---
title: Aktivieren der Funktion (WPF nicht verwaltete API-Referenz)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: ee231653815bd5ef75d58979034e3b3be9f5ba54
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480779"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="e4695-102">Aktivieren der Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e4695-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="e4695-103">Diese API unterstützt die Infrastruktur von Windows Presentation Foundation (WPF) und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e4695-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="e4695-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Windows-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="e4695-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="e4695-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4695-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="e4695-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4695-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="e4695-107">Ein Zeiger auf die Aktivierungsparameter des Fensters.</span><span class="sxs-lookup"><span data-stu-id="e4695-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="e4695-108">Ein Zeiger auf die Adresse eines Puffers, der einen Zeiger auf enthält einem Element eine <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> Objekt.</span><span class="sxs-lookup"><span data-stu-id="e4695-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4695-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4695-109">Requirements</span></span>

<span data-ttu-id="e4695-110">**Plattformen:** Finden Sie unter [Systemanforderungen für .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4695-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e4695-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="e4695-111">**DLL:**</span></span>

<span data-ttu-id="e4695-112">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="e4695-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="e4695-113">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="e4695-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="e4695-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4695-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e4695-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4695-115">See also</span></span>

- [<span data-ttu-id="e4695-116">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="e4695-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
