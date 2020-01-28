---
title: 'Forwardtranslateaccelerator-Funktion: Referenz zur nicht verwalteten WPF-API'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: f6e8208ffe2c186234f30f31e346ca6b1d0be4c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747040"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="d25a5-102">Forwardtranslateaccelerator-Funktion (Referenz zur nicht verwalteten WPF-API)</span><span class="sxs-lookup"><span data-stu-id="d25a5-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="d25a5-103">Diese API unterstützt die Windows Presentation Foundation-Infrastruktur (WPF) und ist nicht für die direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="d25a5-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="d25a5-104">Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Windows-Verwaltung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d25a5-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d25a5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d25a5-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="d25a5-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="d25a5-106">Parameters</span></span>  
 <span data-ttu-id="d25a5-107">pmsg</span><span class="sxs-lookup"><span data-stu-id="d25a5-107">pMsg</span></span>  
 <span data-ttu-id="d25a5-108">Ein Zeiger auf eine Meldung.</span><span class="sxs-lookup"><span data-stu-id="d25a5-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="d25a5-109">appunbehandelte</span><span class="sxs-lookup"><span data-stu-id="d25a5-109">appUnhandled</span></span>  
 <span data-ttu-id="d25a5-110">`true`, wenn der App bereits die Möglichkeit gegeben wurde, die Eingabe Nachricht zu verarbeiten, Sie aber nicht behandelt hat. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d25a5-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d25a5-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d25a5-111">Requirements</span></span>  
 <span data-ttu-id="d25a5-112">**Plattformen:** Siehe [.NET Framework System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d25a5-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d25a5-113">**DLL**</span><span class="sxs-lookup"><span data-stu-id="d25a5-113">**DLL:**</span></span>  
  
 <span data-ttu-id="d25a5-114">In den .NET Framework 3,0 und 3,5: presentationhostdll. dll</span><span class="sxs-lookup"><span data-stu-id="d25a5-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="d25a5-115">In den .NET Framework 4 und höher: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="d25a5-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="d25a5-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d25a5-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d25a5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d25a5-117">See also</span></span>

- [<span data-ttu-id="d25a5-118">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="d25a5-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
