---
title: GetCORSystemDirectory-Funktion
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 008514e3637a980f3722d0c9896a17be33d54c31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431687"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="5eeea-102">GetCORSystemDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="5eeea-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="5eeea-103">Gibt das Installationsverzeichnis der common Language Runtime (CLR), die in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="5eeea-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="5eeea-104">Das Installationsverzeichnis ist vollqualifizierte, z. B. "c:\windows\microsoft.net\framework\v1.0.3705".</span><span class="sxs-lookup"><span data-stu-id="5eeea-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="5eeea-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="5eeea-105">This function is deprecated.</span></span> <span data-ttu-id="5eeea-106">Er ersetzt wird, durch die [ICLRRuntimeInfo:: GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) Methode bereitgestellt wird, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5eeea-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eeea-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5eeea-107">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="5eeea-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="5eeea-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="5eeea-109">[out] Ein Puffer, in dem die Common Language Runtime eine Zeichenfolge zurückgibt, die für die Laufzeit der vollqualifizierte Name des Installationsverzeichnisses enthält, die in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="5eeea-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="5eeea-110">Wenn die Common Language Runtime noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die neueste Version der Laufzeit auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="5eeea-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="5eeea-111">[in] Die Größe in Bytes, der `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="5eeea-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="5eeea-112">[out] Die Anzahl der Zeichen im zurückgegebenen `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="5eeea-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5eeea-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5eeea-113">Remarks</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="5eeea-114">Verwenden Sie diese Funktion nicht in Version 4 der CLR ausgeführten Prozessen.</span><span class="sxs-lookup"><span data-stu-id="5eeea-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="5eeea-115">Wenn eine frühere Version der CLR auf dem Computer installiert ist, gibt diese Funktion das Installationsverzeichnis für die jeweilige Version.</span><span class="sxs-lookup"><span data-stu-id="5eeea-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5eeea-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5eeea-116">Requirements</span></span>  
 <span data-ttu-id="5eeea-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5eeea-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eeea-118">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5eeea-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5eeea-119">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="5eeea-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5eeea-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eeea-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eeea-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5eeea-121">See Also</span></span>  
 [<span data-ttu-id="5eeea-122">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="5eeea-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
