---
title: CallFunctionShim-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CallFunctionShim
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CallFunctionShim
helpviewer_keywords: CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12c399c876a244d0c27e34b41e08c284d7429bac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="a2530-102">CallFunctionShim-Funktion</span><span class="sxs-lookup"><span data-stu-id="a2530-102">CallFunctionShim Function</span></span>
<span data-ttu-id="a2530-103">Ruft eine Funktion mit dem angegebenen Namen und den angegebenen Parametern in der angegebenen Bibliothek auf.</span><span class="sxs-lookup"><span data-stu-id="a2530-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="a2530-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="a2530-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2530-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2530-105">Syntax</span></span>  
  
```  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2530-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a2530-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="a2530-107">[in] Der Name der Bibliothek, die die Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="a2530-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="a2530-108">[in] Der Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="a2530-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="a2530-109">[in] Das erste Argument an die Funktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="a2530-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="a2530-110">[in] Das zweite Argument der Funktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="a2530-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="a2530-111">[in] Die Version der Bibliothek, die die Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="a2530-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="a2530-112">[in] Für zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="a2530-112">[in] Reserved for future use.</span></span> <span data-ttu-id="a2530-113">Übergeben Sie 0 (null), in diesem Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="a2530-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2530-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a2530-114">Requirements</span></span>  
 <span data-ttu-id="a2530-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2530-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2530-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a2530-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2530-117">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="a2530-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2530-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2530-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2530-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2530-119">See Also</span></span>  
 [<span data-ttu-id="a2530-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="a2530-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
