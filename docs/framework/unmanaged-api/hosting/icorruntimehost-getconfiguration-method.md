---
title: ICorRuntimeHost::GetConfiguration-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.GetConfiguration
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61c0a95df2140d2eaf771fcd8f50cd733b9133e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="fd19f-102">ICorRuntimeHost::GetConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="fd19f-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="fd19f-103">Ruft ein Objekt, das den Host an, die Rückrufkonfiguration der common Language Runtime (CLR) ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="fd19f-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd19f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd19f-104">Syntax</span></span>  
  
```  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd19f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd19f-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="fd19f-106">[out] Ein Zeiger auf die Adresse des ein [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) -Objekt, das zum Konfigurieren der CLR verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fd19f-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd19f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd19f-107">Remarks</span></span>  
 <span data-ttu-id="fd19f-108">Die CLR muss vor der Initialisierung konfiguriert sein. andernfalls die `GetConfiguration` Methode gibt einen HRESULT, der angibt, eines Fehlers zurück.</span><span class="sxs-lookup"><span data-stu-id="fd19f-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd19f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd19f-109">Requirements</span></span>  
 <span data-ttu-id="fd19f-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd19f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd19f-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fd19f-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd19f-112">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fd19f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd19f-113">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="fd19f-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd19f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd19f-114">See Also</span></span>  
 [<span data-ttu-id="fd19f-115">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd19f-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
