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
ms.openlocfilehash: c3997415c19483a69e66d8fe68c6ec9241f7ad0d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356210"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="8f576-102">ProcessUnhandledException-Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8f576-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="8f576-103">Diese API unterstützt die Infrastruktur von Windows Presentation Foundation (WPF) und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8f576-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="8f576-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="8f576-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f576-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f576-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f576-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f576-106">Parameters</span></span>  
 <span data-ttu-id="8f576-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="8f576-107">errorMsg</span></span>  
 <span data-ttu-id="8f576-108">Die Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="8f576-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f576-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8f576-109">Requirements</span></span>  
 <span data-ttu-id="8f576-110">**Plattformen:** Finden Sie unter [Systemanforderungen für .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f576-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f576-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="8f576-111">**DLL:**</span></span>  
  
 <span data-ttu-id="8f576-112">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="8f576-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="8f576-113">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="8f576-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="8f576-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f576-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f576-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f576-115">See also</span></span>
- [<span data-ttu-id="8f576-116">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="8f576-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
