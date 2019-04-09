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
ms.openlocfilehash: 4bb7e665bb836dc5f95b14f39179f1d4b9f8173d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080253"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="d8140-102">ForwardTranslateAccelerator-Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d8140-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="d8140-103">Diese API unterstützt die Infrastruktur von Windows Presentation Foundation (WPF) und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8140-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="d8140-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Windows-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="d8140-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8140-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8140-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8140-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d8140-106">Parameters</span></span>  
 <span data-ttu-id="d8140-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="d8140-107">pMsg</span></span>  
 <span data-ttu-id="d8140-108">Ein Zeiger auf eine Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d8140-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="d8140-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="d8140-109">appUnhandled</span></span>  
 `true` <span data-ttu-id="d8140-110">Wenn Sie die app hat bereits wurde die Möglichkeit erhält, die eingabemeldung zu verarbeiten, aber wurde nicht behandelt; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d8140-110">when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8140-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d8140-111">Requirements</span></span>  
 <span data-ttu-id="d8140-112">**Plattformen:** Finden Sie unter [Systemanforderungen für .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8140-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 **<span data-ttu-id="d8140-113">DLL:</span><span class="sxs-lookup"><span data-stu-id="d8140-113">DLL:</span></span>**  
  
 <span data-ttu-id="d8140-114">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="d8140-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="d8140-115">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="d8140-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 **<span data-ttu-id="d8140-116">.NET Framework-Version:</span><span class="sxs-lookup"><span data-stu-id="d8140-116">.NET Framework Version:</span></span>** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8140-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8140-117">See also</span></span>

- [<span data-ttu-id="d8140-118">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="d8140-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
