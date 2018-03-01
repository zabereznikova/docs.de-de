---
title: GetCORSystemDirectory-Funktion
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
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 02b695ac7f75dd38da8cd06e1444af4ae425ebd2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="2c2a9-102">GetCORSystemDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="2c2a9-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="2c2a9-103">Gibt das Installationsverzeichnis der common Language Runtime (CLR), die in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="2c2a9-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="2c2a9-104">Das Installationsverzeichnis ist vollqualifizierte, z. B. "c:\windows\microsoft.net\framework\v1.0.3705".</span><span class="sxs-lookup"><span data-stu-id="2c2a9-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="2c2a9-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="2c2a9-105">This function is deprecated.</span></span> <span data-ttu-id="2c2a9-106">Er ersetzt wird, durch die [ICLRRuntimeInfo:: GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) Methode bereitgestellt wird, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c2a9-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c2a9-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c2a9-107">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c2a9-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c2a9-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="2c2a9-109">[out] Ein Puffer, in dem die Common Language Runtime eine Zeichenfolge zurückgibt, die für die Laufzeit der vollqualifizierte Name des Installationsverzeichnisses enthält, die in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="2c2a9-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="2c2a9-110">Wenn die Common Language Runtime noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die neueste Version der Laufzeit auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="2c2a9-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="2c2a9-111">[in] Die Größe in Bytes, der `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="2c2a9-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="2c2a9-112">[out] Die Anzahl der Zeichen im zurückgegebenen `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="2c2a9-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c2a9-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c2a9-113">Remarks</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="2c2a9-114">Verwenden Sie diese Funktion nicht in Version 4 der CLR ausgeführten Prozessen.</span><span class="sxs-lookup"><span data-stu-id="2c2a9-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="2c2a9-115">Wenn eine frühere Version der CLR auf dem Computer installiert ist, gibt diese Funktion das Installationsverzeichnis für die jeweilige Version.</span><span class="sxs-lookup"><span data-stu-id="2c2a9-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c2a9-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c2a9-116">Requirements</span></span>  
 <span data-ttu-id="2c2a9-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c2a9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c2a9-118">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2c2a9-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c2a9-119">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="2c2a9-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c2a9-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c2a9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c2a9-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c2a9-121">See Also</span></span>  
 [<span data-ttu-id="2c2a9-122">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="2c2a9-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
