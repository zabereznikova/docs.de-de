---
title: GetCORRequiredVersion-Funktion
ms.date: 03/30/2017
api_name:
- GetCORRequiredVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetCORRequiredVersion
helpviewer_keywords:
- GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5786444c36fcfc9547be1db0006757b0a9376c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628098"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="6b74b-102">GetCORRequiredVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="6b74b-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="6b74b-103">Ruft ab, die erforderlich common Language Runtime (CLR)-Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="6b74b-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="6b74b-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="6b74b-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b74b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b74b-105">Syntax</span></span>  
  
```  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b74b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b74b-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="6b74b-107">[out] Ein Puffer mit der eine Zeichenfolge, die Versionsnummer angibt.</span><span class="sxs-lookup"><span data-stu-id="6b74b-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="6b74b-108">[in] Die Größe des Puffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="6b74b-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="6b74b-109">[out] Die Anzahl der Bytes im Puffer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6b74b-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b74b-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b74b-110">Requirements</span></span>  
 <span data-ttu-id="6b74b-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b74b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b74b-112">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6b74b-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6b74b-113">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6b74b-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b74b-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b74b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b74b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b74b-115">See also</span></span>

- [<span data-ttu-id="6b74b-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="6b74b-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
