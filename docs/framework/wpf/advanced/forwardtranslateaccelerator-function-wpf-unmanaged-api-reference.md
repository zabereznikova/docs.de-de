---
title: ForwardTranslateAccelerator-Funktion (WPF nicht verwaltete API-Referenz)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: 78031ed80fe83b736a351886457f9200534f470b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591512"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="08626-102">ForwardTranslateAccelerator-Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="08626-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="08626-103">Diese API unterstützt die Infrastruktur von Windows Presentation Foundation (WPF) und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="08626-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="08626-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Windows-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="08626-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08626-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="08626-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08626-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="08626-106">Parameters</span></span>  
 <span data-ttu-id="08626-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="08626-107">pMsg</span></span>  
 <span data-ttu-id="08626-108">Ein Zeiger auf eine Nachricht.</span><span class="sxs-lookup"><span data-stu-id="08626-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="08626-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="08626-109">appUnhandled</span></span>  
 <span data-ttu-id="08626-110">`true` Wenn Sie die app hat bereits wurde die Möglichkeit erhält, die eingabemeldung zu verarbeiten, aber wurde nicht behandelt; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="08626-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08626-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08626-111">Requirements</span></span>  
 <span data-ttu-id="08626-112">**Plattformen:** Finden Sie unter [Systemanforderungen für .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08626-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08626-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="08626-113">**DLL:**</span></span>  
  
 <span data-ttu-id="08626-114">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="08626-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="08626-115">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="08626-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="08626-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08626-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08626-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08626-117">See also</span></span>
- [<span data-ttu-id="08626-118">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="08626-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
