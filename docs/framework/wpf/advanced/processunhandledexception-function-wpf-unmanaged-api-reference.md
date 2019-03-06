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
ms.openlocfilehash: 3a95e8e68361f060d843247f400043a79dc28889
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466864"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="90252-102">ProcessUnhandledException-Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="90252-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="90252-103">Diese API unterstützt die Infrastruktur von Windows Presentation Foundation (WPF) und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="90252-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="90252-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="90252-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90252-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="90252-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="90252-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="90252-106">Parameters</span></span>  
 <span data-ttu-id="90252-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="90252-107">errorMsg</span></span>  
 <span data-ttu-id="90252-108">Die Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="90252-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90252-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90252-109">Requirements</span></span>  
 <span data-ttu-id="90252-110">**Plattformen:** Finden Sie unter [Systemanforderungen für .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90252-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90252-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="90252-111">**DLL:**</span></span>  
  
 <span data-ttu-id="90252-112">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="90252-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="90252-113">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="90252-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="90252-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90252-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90252-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90252-115">See also</span></span>
- [<span data-ttu-id="90252-116">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="90252-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
