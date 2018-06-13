---
title: ICorRuntimeHost::GetConfiguration-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c51ddae6aa62552bac9990b57a173c28f73bae5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436831"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="3fad2-102">ICorRuntimeHost::GetConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="3fad2-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="3fad2-103">Ruft ein Objekt, das den Host an, die Rückrufkonfiguration der common Language Runtime (CLR) ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3fad2-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fad2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3fad2-104">Syntax</span></span>  
  
```  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fad2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3fad2-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="3fad2-106">[out] Ein Zeiger auf die Adresse des ein [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) -Objekt, das zum Konfigurieren der CLR verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3fad2-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fad2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3fad2-107">Remarks</span></span>  
 <span data-ttu-id="3fad2-108">Die CLR muss vor der Initialisierung konfiguriert sein. andernfalls die `GetConfiguration` Methode gibt einen HRESULT, der angibt, eines Fehlers zurück.</span><span class="sxs-lookup"><span data-stu-id="3fad2-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fad2-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3fad2-109">Requirements</span></span>  
 <span data-ttu-id="3fad2-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fad2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fad2-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3fad2-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fad2-112">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3fad2-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fad2-113">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="3fad2-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fad2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fad2-114">See Also</span></span>  
 [<span data-ttu-id="3fad2-115">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3fad2-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
