---
title: GetFileVersion-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 43e7a1326cad1b831a88c7fc3877679b4c096709
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getfileversion-function"></a><span data-ttu-id="ec123-102">GetFileVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="ec123-102">GetFileVersion Function</span></span>
<span data-ttu-id="ec123-103">Ruft ab, der zur common Language Runtime (CLR) Version der angegebenen Datei unter Verwendung des angegebenen Puffers.</span><span class="sxs-lookup"><span data-stu-id="ec123-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="ec123-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="ec123-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec123-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec123-105">Syntax</span></span>  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec123-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec123-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="ec123-107">[in] Der Pfad der Datei, die untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="ec123-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="ec123-108">[in, out] Pufferspeicher für die Versionsinformationen, die zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ec123-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="ec123-109">[in] Die Größe in Breitzeichen von `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="ec123-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="ec123-110">[out] Die Größe in Bytes, der zurückgegebenen `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="ec123-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec123-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec123-111">Requirements</span></span>  
 <span data-ttu-id="ec123-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec123-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec123-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ec123-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec123-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec123-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec123-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec123-115">See Also</span></span>  
 [<span data-ttu-id="ec123-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="ec123-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
