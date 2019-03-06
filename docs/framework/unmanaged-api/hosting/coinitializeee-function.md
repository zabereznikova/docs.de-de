---
title: CoInitializeEE-Funktion
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 061a54dd3b3700840f90843a135cf81d8ed81a2e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481156"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="41178-102">CoInitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="41178-102">CoInitializeEE Function</span></span>
<span data-ttu-id="41178-103">Stellt sicher, dass die common Language Runtime-Ausführungsmodul in einen Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="41178-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="41178-104">Diese Funktion ist veraltet, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41178-104">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="41178-105">Verwenden der [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="41178-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41178-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="41178-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41178-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="41178-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="41178-108">[in] Eines der [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) Enumerationskonstanten.</span><span class="sxs-lookup"><span data-stu-id="41178-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41178-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="41178-109">Return Value</span></span>  
 <span data-ttu-id="41178-110">Diese Methode gibt die standard-COM-Fehlercodes zurück, wie in "Winerror.h", und die Werte in der folgenden Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="41178-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="41178-111">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="41178-111">Return code</span></span>|<span data-ttu-id="41178-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41178-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="41178-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="41178-113">S_OK</span></span>|<span data-ttu-id="41178-114">Die ausführungs-Engine wurde erfolgreich geladen.</span><span class="sxs-lookup"><span data-stu-id="41178-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="41178-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="41178-115">S_FALSE</span></span>|<span data-ttu-id="41178-116">Die ausführungs-Engine ist bereits geladen.</span><span class="sxs-lookup"><span data-stu-id="41178-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="41178-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="41178-117">E_FAIL</span></span>|<span data-ttu-id="41178-118">Die ausführungs-Engine konnte nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="41178-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41178-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41178-119">Remarks</span></span>  
 <span data-ttu-id="41178-120">Diese Methode lädt die ausführungs-Engine auf, wenn es nicht bereits geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="41178-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41178-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41178-121">Requirements</span></span>  
 <span data-ttu-id="41178-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41178-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41178-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="41178-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41178-124">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="41178-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41178-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41178-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41178-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41178-126">See also</span></span>
- [<span data-ttu-id="41178-127">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="41178-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
