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
ms.openlocfilehash: a4480d54390aea2771e2939b0a0825f6c49c3564
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766131"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="869f7-102">LoadFromHistory-Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="869f7-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="869f7-103">Diese API unterstützt die Infrastruktur von Windows Presentation Foundation (WPF) und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="869f7-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="869f7-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Windows-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="869f7-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="869f7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="869f7-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="869f7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="869f7-106">Parameters</span></span>  
 <span data-ttu-id="869f7-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="869f7-107">pHistoryStream</span></span>  
 <span data-ttu-id="869f7-108">Ein Zeiger auf einen Datenstrom von Verlaufsinformationen.</span><span class="sxs-lookup"><span data-stu-id="869f7-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="869f7-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="869f7-109">pBindCtx</span></span>  
 <span data-ttu-id="869f7-110">Ein Zeiger auf einen Bindungskontext.</span><span class="sxs-lookup"><span data-stu-id="869f7-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="869f7-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="869f7-111">Requirements</span></span>  
 <span data-ttu-id="869f7-112">**Plattformen:** Finden Sie unter [Systemanforderungen für .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="869f7-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="869f7-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="869f7-113">**DLL:**</span></span>  
  
 <span data-ttu-id="869f7-114">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="869f7-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="869f7-115">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="869f7-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="869f7-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="869f7-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="869f7-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="869f7-117">See also</span></span>

- [<span data-ttu-id="869f7-118">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="869f7-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
