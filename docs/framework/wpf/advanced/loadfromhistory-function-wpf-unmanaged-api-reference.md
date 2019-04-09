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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084960"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="3d6fc-102">LoadFromHistory-Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3d6fc-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="3d6fc-103">Diese API unterstützt die Infrastruktur von Windows Presentation Foundation (WPF) und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3d6fc-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="3d6fc-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Windows-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="3d6fc-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d6fc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d6fc-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d6fc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d6fc-106">Parameters</span></span>  
 <span data-ttu-id="3d6fc-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="3d6fc-107">pHistoryStream</span></span>  
 <span data-ttu-id="3d6fc-108">Ein Zeiger auf einen Datenstrom von Verlaufsinformationen.</span><span class="sxs-lookup"><span data-stu-id="3d6fc-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="3d6fc-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="3d6fc-109">pBindCtx</span></span>  
 <span data-ttu-id="3d6fc-110">Ein Zeiger auf einen Bindungskontext.</span><span class="sxs-lookup"><span data-stu-id="3d6fc-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d6fc-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d6fc-111">Requirements</span></span>  
 <span data-ttu-id="3d6fc-112">**Plattformen:** Finden Sie unter [Systemanforderungen für .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d6fc-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 **<span data-ttu-id="3d6fc-113">DLL:</span><span class="sxs-lookup"><span data-stu-id="3d6fc-113">DLL:</span></span>**  
  
 <span data-ttu-id="3d6fc-114">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="3d6fc-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="3d6fc-115">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="3d6fc-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 **<span data-ttu-id="3d6fc-116">.NET Framework-Version:</span><span class="sxs-lookup"><span data-stu-id="3d6fc-116">.NET Framework Version:</span></span>** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3d6fc-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d6fc-117">See also</span></span>

- [<span data-ttu-id="3d6fc-118">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="3d6fc-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
