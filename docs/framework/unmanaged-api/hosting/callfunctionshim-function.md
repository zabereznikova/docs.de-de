---
title: CallFunctionShim-Funktion
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1060ca140db0304c8e5667f7fdf9624b3ac2b64a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429282"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="6acfb-102">CallFunctionShim-Funktion</span><span class="sxs-lookup"><span data-stu-id="6acfb-102">CallFunctionShim Function</span></span>
<span data-ttu-id="6acfb-103">Ruft eine Funktion mit dem angegebenen Namen und den angegebenen Parametern in der angegebenen Bibliothek auf.</span><span class="sxs-lookup"><span data-stu-id="6acfb-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="6acfb-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="6acfb-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6acfb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6acfb-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="6acfb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6acfb-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="6acfb-107">[in] Der Name der Bibliothek, die die Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="6acfb-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="6acfb-108">[in] Der Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="6acfb-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="6acfb-109">[in] Das erste Argument an die Funktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="6acfb-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="6acfb-110">[in] Das zweite Argument der Funktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="6acfb-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="6acfb-111">[in] Die Version der Bibliothek, die die Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="6acfb-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="6acfb-112">[in] Für zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="6acfb-112">[in] Reserved for future use.</span></span> <span data-ttu-id="6acfb-113">Übergeben Sie 0 (null), in diesem Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="6acfb-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6acfb-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6acfb-114">Requirements</span></span>  
 <span data-ttu-id="6acfb-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6acfb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6acfb-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6acfb-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6acfb-117">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="6acfb-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6acfb-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6acfb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6acfb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6acfb-119">See Also</span></span>  
 [<span data-ttu-id="6acfb-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="6acfb-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
