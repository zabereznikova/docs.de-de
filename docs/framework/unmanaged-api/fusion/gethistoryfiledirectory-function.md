---
title: GetHistoryFileDirectory-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHistoryFileDirectory
api_location: fusion.dll
api_type: DLLExport
f1_keywords: GetHistoryFileDirectory
helpviewer_keywords: GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f01100140e9e1dd05cb42b3cfe586c5f6462444c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="c697b-102">GetHistoryFileDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="c697b-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="c697b-103">Ruft den Pfad des Verzeichnisses Verlauf Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="c697b-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c697b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c697b-104">Syntax</span></span>  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c697b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c697b-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="c697b-106">[out] Ein Puffer, der den Pfad im Anwendungsverzeichnis-Verlauf aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c697b-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="c697b-107">[in, out] Die Länge des Puffers.</span><span class="sxs-lookup"><span data-stu-id="c697b-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c697b-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c697b-108">Return Value</span></span>  
 <span data-ttu-id="c697b-109">Diese Methode gibt COM-Standardfehlercodes zurück, wie in der Datei "WinError.h" zusätzlich zu den folgenden Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="c697b-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="c697b-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="c697b-110">Return code</span></span>|<span data-ttu-id="c697b-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c697b-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="c697b-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c697b-112">S_OK</span></span>|<span data-ttu-id="c697b-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c697b-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="c697b-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c697b-114">E_INVALIDARG</span></span>|<span data-ttu-id="c697b-115">`wzDir`oder `pdwSize` ist Null, oder die Version Zeichenfolge ist falsch.</span><span class="sxs-lookup"><span data-stu-id="c697b-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c697b-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c697b-116">Remarks</span></span>  
 <span data-ttu-id="c697b-117">Bei erfolgreichem Abschluss der `pdwSize` -Argument auf die Länge der Zeichenfolge für den Pfad festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c697b-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c697b-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c697b-118">Requirements</span></span>  
 <span data-ttu-id="c697b-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c697b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c697b-120">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c697b-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c697b-121">**Bibliothek:** Fusion.dll und "Mscorwks.dll".</span><span class="sxs-lookup"><span data-stu-id="c697b-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="c697b-122">Verwenden Sie Fusion.dll anstelle von "Mscorwks.dll", um sicherzustellen, dass Sie die richtige Version von .NET Framework abzielen.</span><span class="sxs-lookup"><span data-stu-id="c697b-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="c697b-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c697b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c697b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c697b-124">See Also</span></span>  
 [<span data-ttu-id="c697b-125">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="c697b-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="c697b-126">NukeDownloadedCache-Funktion</span><span class="sxs-lookup"><span data-stu-id="c697b-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 [<span data-ttu-id="c697b-127">Globale statische Fusionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="c697b-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
