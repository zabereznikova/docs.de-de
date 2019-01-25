---
title: Aktivieren der Funktion (WPF nicht verwaltete API-Referenz)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Acrivate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 4e79b74dc8bb7d57125c27e17e8f52d607fffcf1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721980"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="0929d-102">Aktivieren der Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0929d-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="0929d-103">Diese API unterstützt die Infrastruktur von Windows Presentation Foundation (WPF) und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0929d-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="0929d-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Windows-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="0929d-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0929d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0929d-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0929d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0929d-106">Parameters</span></span>  
 <span data-ttu-id="0929d-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="0929d-107">pParameters</span></span>  
 <span data-ttu-id="0929d-108">Ein Zeiger auf die Aktivierungsparameter des Fensters.</span><span class="sxs-lookup"><span data-stu-id="0929d-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="0929d-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="0929d-109">ppInner</span></span>  
 <span data-ttu-id="0929d-110">Ein Zeiger auf die Adresse eines Puffers, der einen Zeiger auf enthält einem Element eine <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> Objekt.</span><span class="sxs-lookup"><span data-stu-id="0929d-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0929d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0929d-111">Requirements</span></span>  
 <span data-ttu-id="0929d-112">**Plattformen:** Finden Sie unter [Systemanforderungen für .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0929d-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0929d-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="0929d-113">**DLL:**</span></span>  
  
 <span data-ttu-id="0929d-114">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="0929d-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="0929d-115">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="0929d-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="0929d-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0929d-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0929d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0929d-117">See also</span></span>
- [<span data-ttu-id="0929d-118">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="0929d-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
