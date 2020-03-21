---
title: ForwardTranslateAccelerator-Funktion - Nicht verwalteter WPF-API-Verweis
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: a0a01be3000dc53df7855cb74015ba1164206838
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186633"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="29f41-102">ForwardTranslateAccelerator-Funktion (WPF-Referenz für nicht verwaltete API)</span><span class="sxs-lookup"><span data-stu-id="29f41-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="29f41-103">Diese API unterstützt die Windows Presentation Foundation (WPF)-Infrastruktur und ist nicht für die direkte Verwendung aus ihrem Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="29f41-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="29f41-104">Wird von der Windows Presentation Foundation (WPF)-Infrastruktur für die Windows-Verwaltung verwendet.</span><span class="sxs-lookup"><span data-stu-id="29f41-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29f41-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="29f41-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="29f41-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="29f41-106">Parameters</span></span>  
 <span data-ttu-id="29f41-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="29f41-107">pMsg</span></span>  
 <span data-ttu-id="29f41-108">Ein Zeiger auf eine Nachricht.</span><span class="sxs-lookup"><span data-stu-id="29f41-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="29f41-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="29f41-109">appUnhandled</span></span>  
 <span data-ttu-id="29f41-110">`true`wenn der App bereits die Möglichkeit gegeben wurde, die Eingabenachricht zu verarbeiten, sie jedoch nicht behandelt wurde. andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="29f41-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29f41-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="29f41-111">Requirements</span></span>  
 <span data-ttu-id="29f41-112">**Plattformen:** Siehe [.NET Framework Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29f41-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29f41-113">**Dll:**</span><span class="sxs-lookup"><span data-stu-id="29f41-113">**DLL:**</span></span>  
  
 <span data-ttu-id="29f41-114">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="29f41-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="29f41-115">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="29f41-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="29f41-116">**.NET Framework-Version:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29f41-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29f41-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29f41-117">See also</span></span>

- [<span data-ttu-id="29f41-118">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="29f41-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
