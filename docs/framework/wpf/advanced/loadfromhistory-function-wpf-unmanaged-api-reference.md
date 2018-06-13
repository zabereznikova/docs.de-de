---
title: LoadFromHistory-Funktion (WPF nicht verwaltete API-Referenz)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 19674b45af84e1e6a6ca169f7b6654c6e3847416
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544663"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="d6950-102">LoadFromHistory-Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d6950-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="d6950-103">Diese API unterstützt die Windows Presentation Foundation (WPF)-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6950-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="d6950-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Verwaltung von Windows.</span><span class="sxs-lookup"><span data-stu-id="d6950-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6950-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6950-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6950-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6950-106">Parameters</span></span>  
 <span data-ttu-id="d6950-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="d6950-107">pHistoryStream</span></span>  
 <span data-ttu-id="d6950-108">Ein Zeiger auf einen Datenstrom von Verlaufsinformationen.</span><span class="sxs-lookup"><span data-stu-id="d6950-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="d6950-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="d6950-109">pBindCtx</span></span>  
 <span data-ttu-id="d6950-110">Ein Zeiger auf einen Bindungskontext.</span><span class="sxs-lookup"><span data-stu-id="d6950-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6950-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d6950-111">Requirements</span></span>  
 <span data-ttu-id="d6950-112">**Plattformen:** finden Sie unter [Systemanforderungen für .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6950-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6950-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="d6950-113">**DLL:**</span></span>  
  
 <span data-ttu-id="d6950-114">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="d6950-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="d6950-115">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="d6950-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="d6950-116">**.NET Framework-Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6950-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6950-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6950-117">See Also</span></span>  
 [<span data-ttu-id="d6950-118">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="d6950-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
