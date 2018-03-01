---
title: GetHistoryFileDirectory-Funktion
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
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5d0ec18a4f95d0d280a66b3b9d9200c560f5f187
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="0fd10-102">GetHistoryFileDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="0fd10-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="0fd10-103">Ruft den Pfad des Verzeichnisses Verlauf Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="0fd10-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fd10-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0fd10-104">Syntax</span></span>  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fd10-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0fd10-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="0fd10-106">[out] Ein Puffer, der den Pfad im Anwendungsverzeichnis-Verlauf aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="0fd10-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="0fd10-107">[in, out] Die Länge des Puffers.</span><span class="sxs-lookup"><span data-stu-id="0fd10-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0fd10-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0fd10-108">Return Value</span></span>  
 <span data-ttu-id="0fd10-109">Diese Methode gibt COM-Standardfehlercodes zurück, wie in der Datei "WinError.h" zusätzlich zu den folgenden Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="0fd10-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="0fd10-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="0fd10-110">Return code</span></span>|<span data-ttu-id="0fd10-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0fd10-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="0fd10-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0fd10-112">S_OK</span></span>|<span data-ttu-id="0fd10-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0fd10-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="0fd10-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0fd10-114">E_INVALIDARG</span></span>|<span data-ttu-id="0fd10-115">`wzDir`oder `pdwSize` ist Null, oder die Version Zeichenfolge ist falsch.</span><span class="sxs-lookup"><span data-stu-id="0fd10-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fd10-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0fd10-116">Remarks</span></span>  
 <span data-ttu-id="0fd10-117">Bei erfolgreichem Abschluss der `pdwSize` -Argument auf die Länge der Zeichenfolge für den Pfad festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="0fd10-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fd10-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0fd10-118">Requirements</span></span>  
 <span data-ttu-id="0fd10-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fd10-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fd10-120">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0fd10-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0fd10-121">**Bibliothek:** Fusion.dll und "Mscorwks.dll".</span><span class="sxs-lookup"><span data-stu-id="0fd10-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="0fd10-122">Verwenden Sie Fusion.dll anstelle von "Mscorwks.dll", um sicherzustellen, dass Sie die richtige Version von .NET Framework abzielen.</span><span class="sxs-lookup"><span data-stu-id="0fd10-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="0fd10-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fd10-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fd10-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fd10-124">See Also</span></span>  
 [<span data-ttu-id="0fd10-125">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="0fd10-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="0fd10-126">NukeDownloadedCache-Funktion</span><span class="sxs-lookup"><span data-stu-id="0fd10-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 [<span data-ttu-id="0fd10-127">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="0fd10-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
