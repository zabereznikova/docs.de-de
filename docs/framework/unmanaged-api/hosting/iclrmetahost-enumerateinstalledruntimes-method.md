---
title: ICLRMetaHost::EnumerateInstalledRuntimes-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
ms.openlocfilehash: c99607bfe5fda01eb1abfd7771cb3907ddabeec5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703775"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="5d84f-102">ICLRMetaHost::EnumerateInstalledRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="5d84f-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="5d84f-103">Gibt eine Enumeration zurück, die eine gültige [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle für jede Version der Common Language Runtime (CLR) enthält, die auf einem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5d84f-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d84f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d84f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d84f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d84f-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="5d84f-106">vorgenommen Eine Enumeration von [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstellen, die jeder Version der CLR entsprechen, die auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5d84f-106">[out] An enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d84f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5d84f-107">Return Value</span></span>  
 <span data-ttu-id="5d84f-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5d84f-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5d84f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d84f-109">HRESULT</span></span>|<span data-ttu-id="5d84f-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5d84f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d84f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d84f-111">S_OK</span></span>|<span data-ttu-id="5d84f-112">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5d84f-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="5d84f-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="5d84f-113">E_POINTER</span></span>|<span data-ttu-id="5d84f-114">`ppEnumerator` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="5d84f-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d84f-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d84f-115">Requirements</span></span>  
 <span data-ttu-id="5d84f-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d84f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d84f-117">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="5d84f-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5d84f-118">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5d84f-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d84f-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d84f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d84f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d84f-120">See also</span></span>

- [<span data-ttu-id="5d84f-121">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d84f-121">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="5d84f-122">Hosting</span><span class="sxs-lookup"><span data-stu-id="5d84f-122">Hosting</span></span>](index.md)
