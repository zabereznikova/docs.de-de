---
title: ICLRRuntimeInfo::LoadErrorString-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
ms.openlocfilehash: 0e029aa848a6630ae00c834dd2b924dc4ebce537
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671771"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="d7cd7-102">ICLRRuntimeInfo::LoadErrorString-Methode</span><span class="sxs-lookup"><span data-stu-id="d7cd7-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>

<span data-ttu-id="d7cd7-103">Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.</span><span class="sxs-lookup"><span data-stu-id="d7cd7-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="d7cd7-104">Diese Methode ersetzt die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="d7cd7-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="d7cd7-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="d7cd7-105">LoadStringRC</span></span>](loadstringrc-function.md)  
  
- [<span data-ttu-id="d7cd7-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="d7cd7-106">LoadStringRCEx</span></span>](loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="d7cd7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7cd7-107">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7cd7-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7cd7-108">Parameters</span></span>  

 `iResourceID`  
 <span data-ttu-id="d7cd7-109">in Das zu über setzende HRESULT.</span><span class="sxs-lookup"><span data-stu-id="d7cd7-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="d7cd7-110">vorgenommen Die dem angegebenen HRESULT zugeordnete Meldungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d7cd7-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="d7cd7-111">[in, out] Die Größe von `pwzbuffer` , um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="d7cd7-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="d7cd7-112">Wenn `pwzbuffer` NULL ist, wird `pcchBuffer` die erwartete Größe von bereitgestellt `pwzbuffer` , um die vorab Zuordnung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="d7cd7-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="d7cd7-113">in Der Kultur Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="d7cd7-113">[in] The culture identifier.</span></span> <span data-ttu-id="d7cd7-114">Wenn Sie die Standard Kultur verwenden möchten, müssen Sie-1 angeben.</span><span class="sxs-lookup"><span data-stu-id="d7cd7-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7cd7-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d7cd7-115">Return Value</span></span>  

 <span data-ttu-id="d7cd7-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d7cd7-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d7cd7-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d7cd7-117">HRESULT</span></span>|<span data-ttu-id="d7cd7-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d7cd7-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d7cd7-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7cd7-119">S_OK</span></span>|<span data-ttu-id="d7cd7-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d7cd7-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="d7cd7-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d7cd7-121">E_POINTER</span></span>|<span data-ttu-id="d7cd7-122">`pcchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="d7cd7-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="d7cd7-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d7cd7-123">E_INVALIDARG</span></span>|<span data-ttu-id="d7cd7-124">`pwzBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="d7cd7-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d7cd7-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d7cd7-125">Requirements</span></span>  

 <span data-ttu-id="d7cd7-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7cd7-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7cd7-127">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="d7cd7-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d7cd7-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d7cd7-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d7cd7-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7cd7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7cd7-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7cd7-130">See also</span></span>

- [<span data-ttu-id="d7cd7-131">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7cd7-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="d7cd7-132">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d7cd7-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="d7cd7-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="d7cd7-133">Hosting</span></span>](index.md)
