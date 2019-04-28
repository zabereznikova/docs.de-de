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
ms.openlocfilehash: 7aeb813cafbf5b18739c4574c386398ac3c7a77b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778000"
---
# <a name="callfunctionshim-function"></a><span data-ttu-id="f2d5a-102">CallFunctionShim-Funktion</span><span class="sxs-lookup"><span data-stu-id="f2d5a-102">CallFunctionShim Function</span></span>
<span data-ttu-id="f2d5a-103">Ruft eine Funktion mit dem angegebenen Namen und den angegebenen Parametern in der angegebenen Bibliothek auf.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-103">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 <span data-ttu-id="f2d5a-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2d5a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2d5a-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="f2d5a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2d5a-106">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="f2d5a-107">[in] Der Name der Bibliothek, die die Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-107">[in] The name of the library containing the function.</span></span>  
  
 `szFunctionName`  
 <span data-ttu-id="f2d5a-108">[in] Der Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-108">[in] The name of the function.</span></span>  
  
 `lpvArgument1`  
 <span data-ttu-id="f2d5a-109">[in] Das erste Argument an die Funktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-109">[in] The first argument to pass to the function.</span></span>  
  
 `lpvArgument2`  
 <span data-ttu-id="f2d5a-110">[in] Das zweite Argument an die Funktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-110">[in] The second argument to pass to the function.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="f2d5a-111">[in] Die Version der Bibliothek, die die Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-111">[in] The version of the library that contains the function.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="f2d5a-112">[in] Für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-112">[in] Reserved for future use.</span></span> <span data-ttu-id="f2d5a-113">Übergeben Sie 0 (null), in diesem Parameter.</span><span class="sxs-lookup"><span data-stu-id="f2d5a-113">Pass zero in this parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2d5a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f2d5a-114">Requirements</span></span>  
 <span data-ttu-id="f2d5a-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2d5a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2d5a-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2d5a-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2d5a-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2d5a-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2d5a-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2d5a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2d5a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2d5a-119">See also</span></span>

- [<span data-ttu-id="f2d5a-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="f2d5a-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
