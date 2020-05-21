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
ms.openlocfilehash: da6efae38cd70a68feea56b12e86be23fde7f0cb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762187"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="176d6-102">ICLRRuntimeInfo::LoadErrorString-Methode</span><span class="sxs-lookup"><span data-stu-id="176d6-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="176d6-103">Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.</span><span class="sxs-lookup"><span data-stu-id="176d6-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="176d6-104">Diese Methode ersetzt die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="176d6-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="176d6-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="176d6-105">LoadStringRC</span></span>](loadstringrc-function.md)  
  
- [<span data-ttu-id="176d6-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="176d6-106">LoadStringRCEx</span></span>](loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="176d6-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="176d6-107">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="176d6-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="176d6-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="176d6-109">in Das zu über setzende HRESULT.</span><span class="sxs-lookup"><span data-stu-id="176d6-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="176d6-110">vorgenommen Die dem angegebenen HRESULT zugeordnete Meldungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="176d6-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="176d6-111">[in, out] Die Größe von `pwzbuffer` , um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="176d6-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="176d6-112">Wenn `pwzbuffer` NULL ist, wird `pcchBuffer` die erwartete Größe von bereitgestellt `pwzbuffer` , um die vorab Zuordnung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="176d6-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="176d6-113">in Der Kultur Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="176d6-113">[in] The culture identifier.</span></span> <span data-ttu-id="176d6-114">Wenn Sie die Standard Kultur verwenden möchten, müssen Sie-1 angeben.</span><span class="sxs-lookup"><span data-stu-id="176d6-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="176d6-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="176d6-115">Return Value</span></span>  
 <span data-ttu-id="176d6-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="176d6-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="176d6-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="176d6-117">HRESULT</span></span>|<span data-ttu-id="176d6-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="176d6-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="176d6-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="176d6-119">S_OK</span></span>|<span data-ttu-id="176d6-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="176d6-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="176d6-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="176d6-121">E_POINTER</span></span>|<span data-ttu-id="176d6-122">`pcchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="176d6-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="176d6-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="176d6-123">E_INVALIDARG</span></span>|<span data-ttu-id="176d6-124">`pwzBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="176d6-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="176d6-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="176d6-125">Requirements</span></span>  
 <span data-ttu-id="176d6-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="176d6-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="176d6-127">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="176d6-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="176d6-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="176d6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="176d6-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="176d6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="176d6-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="176d6-130">See also</span></span>

- [<span data-ttu-id="176d6-131">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="176d6-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="176d6-132">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="176d6-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="176d6-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="176d6-133">Hosting</span></span>](index.md)
