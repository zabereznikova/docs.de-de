---
title: ProcessUnhandledException-Funktion (WPF nicht verwaltete API-Referenz)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 73480f7cd8be7bcb5296782a8503eb689442a14c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578639"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="47b2f-102">ProcessUnhandledException-Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="47b2f-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="47b2f-103">Diese API unterstützt die Infrastruktur von Windows Presentation Foundation (WPF) und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="47b2f-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="47b2f-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="47b2f-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47b2f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="47b2f-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47b2f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="47b2f-106">Parameters</span></span>  
 <span data-ttu-id="47b2f-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="47b2f-107">errorMsg</span></span>  
 <span data-ttu-id="47b2f-108">Die Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="47b2f-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47b2f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47b2f-109">Requirements</span></span>  
 <span data-ttu-id="47b2f-110">**Plattformen:** Finden Sie unter [Systemanforderungen für .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47b2f-110">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47b2f-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="47b2f-111">**DLL:**</span></span>  
  
 <span data-ttu-id="47b2f-112">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="47b2f-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="47b2f-113">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="47b2f-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="47b2f-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47b2f-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47b2f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47b2f-115">See also</span></span>
- [<span data-ttu-id="47b2f-116">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="47b2f-116">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
