---
title: ForwardTranslateAccelerator-Funktion (WPF nicht verwaltete API-Referenz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: ForwardTranslateAccelerator
api_location: PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cca9c78eaf13e04d22fce9f61ce4a7ab9ee09769
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="f44c4-102">ForwardTranslateAccelerator-Funktion (WPF nicht verwaltete API-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f44c4-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="f44c4-103">Diese API unterstützt die Windows Presentation Foundation (WPF)-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f44c4-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="f44c4-104">Von der Windows Presentation Foundation (WPF)-Infrastruktur verwendet, für die Verwaltung von Windows.</span><span class="sxs-lookup"><span data-stu-id="f44c4-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f44c4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f44c4-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f44c4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f44c4-106">Parameters</span></span>  
 <span data-ttu-id="f44c4-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="f44c4-107">pMsg</span></span>  
 <span data-ttu-id="f44c4-108">Ein Zeiger auf eine Nachricht.</span><span class="sxs-lookup"><span data-stu-id="f44c4-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="f44c4-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="f44c4-109">appUnhandled</span></span>  
 <span data-ttu-id="f44c4-110">`true`Wenn Sie die app bereits Möglichkeit zum Verarbeiten der Eingabenachricht zugewiesen wurde, aber wurde nicht behandelt; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="f44c4-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f44c4-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f44c4-111">Requirements</span></span>  
 <span data-ttu-id="f44c4-112">**Plattformen:** finden Sie unter [Systemanforderungen für .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f44c4-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f44c4-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="f44c4-113">**DLL:**</span></span>  
  
 <span data-ttu-id="f44c4-114">In .NET Framework 3.0 und 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="f44c4-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="f44c4-115">In .NET Framework 4 und höher: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="f44c4-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="f44c4-116">**.NET Framework-Version:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f44c4-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f44c4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f44c4-117">See Also</span></span>  
 [<span data-ttu-id="f44c4-118">WPF – Referenz zur nicht verwalteten API</span><span class="sxs-lookup"><span data-stu-id="f44c4-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
