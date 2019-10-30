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
ms.openlocfilehash: 1aabfad14ee2eb35916bbf115631602276cd1fc3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109891"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="5dc08-102">GetHistoryFileDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="5dc08-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="5dc08-103">Ruft den Pfad des Verzeichnisses für den Anwendungs Verlauf ab.</span><span class="sxs-lookup"><span data-stu-id="5dc08-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dc08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5dc08-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dc08-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5dc08-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="5dc08-106">vorgenommen Ein Puffer, der den Pfad zum Anwendungs Verlaufs Verzeichnis enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="5dc08-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="5dc08-107">[in, out] Die Länge des Puffers.</span><span class="sxs-lookup"><span data-stu-id="5dc08-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5dc08-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5dc08-108">Return Value</span></span>  
 <span data-ttu-id="5dc08-109">Diese Methode gibt Standard-COM-Fehlercodes zurück, die in der Datei "Winerror. h" zusätzlich zu den folgenden Werten definiert sind.</span><span class="sxs-lookup"><span data-stu-id="5dc08-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="5dc08-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="5dc08-110">Return code</span></span>|<span data-ttu-id="5dc08-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5dc08-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5dc08-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5dc08-112">S_OK</span></span>|<span data-ttu-id="5dc08-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5dc08-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="5dc08-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5dc08-114">E_INVALIDARG</span></span>|<span data-ttu-id="5dc08-115">`wzDir` oder `pdwSize` ist NULL, oder die Versions Zeichenfolge ist falsch.</span><span class="sxs-lookup"><span data-stu-id="5dc08-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5dc08-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5dc08-116">Remarks</span></span>  
 <span data-ttu-id="5dc08-117">Nach erfolgreichem Abschluss wird das `pdwSize`-Argument auf die Länge der Pfad Zeichenfolge festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5dc08-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dc08-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5dc08-118">Requirements</span></span>  
 <span data-ttu-id="5dc08-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dc08-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dc08-120">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5dc08-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5dc08-121">**Bibliothek:** "Fusion. dll" und "mscorwert. dll".</span><span class="sxs-lookup"><span data-stu-id="5dc08-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="5dc08-122">Verwenden Sie "Fusion. dll" anstelle von "mscorwert. dll", um sicherzustellen, dass Sie die richtige Version des .NET Framework als Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="5dc08-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="5dc08-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dc08-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dc08-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dc08-124">See also</span></span>

- [<span data-ttu-id="5dc08-125">CreateHistoryReader-Funktion</span><span class="sxs-lookup"><span data-stu-id="5dc08-125">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="5dc08-126">NukeDownloadedCache-Funktion</span><span class="sxs-lookup"><span data-stu-id="5dc08-126">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)
- [<span data-ttu-id="5dc08-127">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="5dc08-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
