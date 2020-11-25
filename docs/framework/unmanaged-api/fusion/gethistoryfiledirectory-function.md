---
title: GetHistoryFileDirectory-Funktion
ms.date: 03/30/2017
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
ms.openlocfilehash: 484adf288356b9955fe0cac0bb30002ec1f012d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724437"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="2d470-102">GetHistoryFileDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="2d470-102">GetHistoryFileDirectory Function</span></span>

<span data-ttu-id="2d470-103">Ruft den Pfad des Verzeichnisses für den Anwendungs Verlauf ab.</span><span class="sxs-lookup"><span data-stu-id="2d470-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d470-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d470-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d470-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d470-105">Parameters</span></span>  

 `wzDir`  
 <span data-ttu-id="2d470-106">vorgenommen Ein Puffer, der den Pfad zum Anwendungs Verlaufs Verzeichnis enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="2d470-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="2d470-107">[in, out] Die Länge des Puffers.</span><span class="sxs-lookup"><span data-stu-id="2d470-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d470-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2d470-108">Return Value</span></span>  

 <span data-ttu-id="2d470-109">Diese Methode gibt Standard-COM-Fehlercodes zurück, die in der Datei "Winerror. h" zusätzlich zu den folgenden Werten definiert sind.</span><span class="sxs-lookup"><span data-stu-id="2d470-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="2d470-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="2d470-110">Return code</span></span>|<span data-ttu-id="2d470-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2d470-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="2d470-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d470-112">S_OK</span></span>|<span data-ttu-id="2d470-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2d470-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="2d470-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2d470-114">E_INVALIDARG</span></span>|<span data-ttu-id="2d470-115">`wzDir` oder `pdwSize` ist NULL, oder die Versions Zeichenfolge ist falsch.</span><span class="sxs-lookup"><span data-stu-id="2d470-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d470-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d470-116">Remarks</span></span>  

 <span data-ttu-id="2d470-117">Nach erfolgreichem Abschluss wird das- `pdwSize` Argument auf die Länge der Pfad Zeichenfolge festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2d470-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d470-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2d470-118">Requirements</span></span>  

 <span data-ttu-id="2d470-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d470-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d470-120">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2d470-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2d470-121">**Bibliothek:** Fusion.dll und Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="2d470-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="2d470-122">Verwenden Sie Fusion.dll anstelle von Mscorwks.dll, um sicherzustellen, dass Sie die richtige Version der .NET Framework als Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d470-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="2d470-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d470-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d470-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d470-124">See also</span></span>

- [<span data-ttu-id="2d470-125">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="2d470-125">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="2d470-126">NukeDownloadedCache-Funktion</span><span class="sxs-lookup"><span data-stu-id="2d470-126">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)
- [<span data-ttu-id="2d470-127">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="2d470-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
