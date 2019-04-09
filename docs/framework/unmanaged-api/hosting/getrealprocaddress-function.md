---
title: GetRealProcAddress-Funktion
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d4723fbf2311316184cb77c90754d7e037badcd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089581"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="b42e0-102">GetRealProcAddress-Funktion</span><span class="sxs-lookup"><span data-stu-id="b42e0-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="b42e0-103">Ruft die Adresse der angegebenen Funktion, die aus der neuesten installierten Version der common Language Runtime (CLR) exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="b42e0-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="b42e0-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="b42e0-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b42e0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b42e0-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b42e0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b42e0-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="b42e0-107">[in] Der Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="b42e0-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="b42e0-108">[out] Der Speicherort, der einen Zeiger auf die Adresse der Funktion empfängt.</span><span class="sxs-lookup"><span data-stu-id="b42e0-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b42e0-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b42e0-109">Return Value</span></span>  
 <span data-ttu-id="b42e0-110">Diese Methode gibt Component Object Model (COM) Standardfehlercodes in "Winerror.h", zusätzlich zu den folgenden Werten in WinError.h definiert.</span><span class="sxs-lookup"><span data-stu-id="b42e0-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="b42e0-111">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="b42e0-111">Return code</span></span>|<span data-ttu-id="b42e0-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b42e0-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b42e0-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b42e0-113">S_OK</span></span>|<span data-ttu-id="b42e0-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b42e0-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="b42e0-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b42e0-115">E_POINTER</span></span>|`ppv` <span data-ttu-id="b42e0-116">ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="b42e0-116">is not valid.</span></span>|  
|<span data-ttu-id="b42e0-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="b42e0-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="b42e0-118">Die Funktion wird von der Laufzeit nicht exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="b42e0-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b42e0-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b42e0-119">Requirements</span></span>  
 <span data-ttu-id="b42e0-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b42e0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b42e0-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b42e0-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b42e0-122">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b42e0-122">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b42e0-123">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="b42e0-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b42e0-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b42e0-124">See also</span></span>

- [<span data-ttu-id="b42e0-125">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="b42e0-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
