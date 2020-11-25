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
ms.openlocfilehash: 2a50814a67be5a01a7413050683a915355665f3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720645"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="e6491-102">ICorRuntimeHost::GetConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="e6491-102">ICorRuntimeHost::GetConfiguration Method</span></span>

<span data-ttu-id="e6491-103">Ruft ein Objekt ab, mit dem der Host die Rückruf Konfiguration des Common Language Runtime (CLR) angeben kann.</span><span class="sxs-lookup"><span data-stu-id="e6491-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6491-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6491-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6491-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e6491-105">Parameters</span></span>  

 `pConfiguration`  
 <span data-ttu-id="e6491-106">vorgenommen Ein Zeiger auf die Adresse eines [ICorConfiguration](icorconfiguration-interface.md) -Objekts, das verwendet werden kann, um die CLR zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e6491-106">[out] A pointer to the address of an [ICorConfiguration](icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6491-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6491-107">Remarks</span></span>  

 <span data-ttu-id="e6491-108">Die CLR muss vor der Initialisierung konfiguriert werden. Andernfalls gibt die `GetConfiguration` Methode ein HRESULT zurück, das auf einen Fehler hinweist.</span><span class="sxs-lookup"><span data-stu-id="e6491-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6491-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e6491-109">Requirements</span></span>  

 <span data-ttu-id="e6491-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6491-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6491-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e6491-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6491-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e6491-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6491-113">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e6491-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6491-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e6491-114">See also</span></span>

- [<span data-ttu-id="e6491-115">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6491-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
