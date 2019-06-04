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
ms.openlocfilehash: ddb9792c00d6b78b29b66bbc3ef59ee4ad8bd81d
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490402"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="2d528-102">GetCORRequiredVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="2d528-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="2d528-103">Ruft ab, die erforderlich common Language Runtime (CLR)-Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="2d528-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="2d528-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="2d528-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d528-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d528-105">Syntax</span></span>  
  
```  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d528-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d528-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="2d528-107">[out] Ein Puffer mit der eine Zeichenfolge, die Versionsnummer angibt.</span><span class="sxs-lookup"><span data-stu-id="2d528-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="2d528-108">[in] Die Größe des Puffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="2d528-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="2d528-109">[out] Die Anzahl der Bytes im Puffer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d528-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d528-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2d528-110">Requirements</span></span>  
 <span data-ttu-id="2d528-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d528-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d528-112">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2d528-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d528-113">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2d528-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d528-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d528-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d528-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d528-115">See also</span></span>

- [<span data-ttu-id="2d528-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="2d528-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
