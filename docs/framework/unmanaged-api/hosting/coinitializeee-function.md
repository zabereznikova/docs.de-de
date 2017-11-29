---
title: CoInitializeEE-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoInitializeEE
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoInitializeEE
helpviewer_keywords: CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 429d055ec0853d04f794b063a76a395d98aceb4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="coinitializeee-function"></a><span data-ttu-id="b7daa-102">CoInitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="b7daa-102">CoInitializeEE Function</span></span>
<span data-ttu-id="b7daa-103">Stellt sicher, dass das Ausführungsmodul der common Language Runtime in einen Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="b7daa-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="b7daa-104">Diese Funktion ist veraltet, der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7daa-104">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="b7daa-105">Verwenden der [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="b7daa-105">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7daa-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7daa-106">Syntax</span></span>  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7daa-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="b7daa-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="b7daa-108">[in] Eines der [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) Enumerationskonstanten.</span><span class="sxs-lookup"><span data-stu-id="b7daa-108">[in] One of the [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7daa-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b7daa-109">Return Value</span></span>  
 <span data-ttu-id="b7daa-110">Diese Methode gibt die standard-COM-Fehlercodes zurück, wie in der Datei "Winerror.h", und die Werte in der folgenden Tabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="b7daa-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="b7daa-111">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="b7daa-111">Return code</span></span>|<span data-ttu-id="b7daa-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7daa-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b7daa-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b7daa-113">S_OK</span></span>|<span data-ttu-id="b7daa-114">Das Ausführungsmodul wurde erfolgreich geladen.</span><span class="sxs-lookup"><span data-stu-id="b7daa-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="b7daa-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b7daa-115">S_FALSE</span></span>|<span data-ttu-id="b7daa-116">Das Ausführungsmodul ist bereits geladen.</span><span class="sxs-lookup"><span data-stu-id="b7daa-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="b7daa-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b7daa-117">E_FAIL</span></span>|<span data-ttu-id="b7daa-118">Das Ausführungsmodul konnte nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="b7daa-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7daa-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7daa-119">Remarks</span></span>  
 <span data-ttu-id="b7daa-120">Diese Methode lädt das Ausführungsmodul, wenn es nicht bereits geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="b7daa-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7daa-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b7daa-121">Requirements</span></span>  
 <span data-ttu-id="b7daa-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7daa-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7daa-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b7daa-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7daa-124">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b7daa-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b7daa-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7daa-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7daa-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7daa-126">See Also</span></span>  
 [<span data-ttu-id="b7daa-127">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="b7daa-127">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
