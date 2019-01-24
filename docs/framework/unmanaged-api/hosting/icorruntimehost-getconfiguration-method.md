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
ms.openlocfilehash: b10ec088f087c45b8a75805e326bc543bb64b3d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665083"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="132d0-102">ICorRuntimeHost::GetConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="132d0-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="132d0-103">Ruft ein Objekt, das den Host Geben Sie die Rückrufkonfiguration, der die common Language Runtime (CLR) ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="132d0-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="132d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="132d0-104">Syntax</span></span>  
  
```  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="132d0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="132d0-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="132d0-106">[out] Ein Zeiger auf die Adresse einer [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) -Objekt, das zum Konfigurieren der CLR verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="132d0-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="132d0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="132d0-107">Remarks</span></span>  
 <span data-ttu-id="132d0-108">Die CLR muss vor der Initialisierung so konfiguriert werden. andernfalls die `GetConfiguration` Methode gibt einen HRESULT, der angibt, eines Fehlers zurück.</span><span class="sxs-lookup"><span data-stu-id="132d0-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="132d0-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="132d0-109">Requirements</span></span>  
 <span data-ttu-id="132d0-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="132d0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="132d0-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="132d0-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="132d0-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="132d0-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="132d0-113">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="132d0-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="132d0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="132d0-114">See also</span></span>
- [<span data-ttu-id="132d0-115">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="132d0-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
