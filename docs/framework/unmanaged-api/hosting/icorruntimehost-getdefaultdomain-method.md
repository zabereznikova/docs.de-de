---
title: ICorRuntimeHost::GetDefaultDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41a6c5ee73cad77368e83792d11d455d8fb163fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937029"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a><span data-ttu-id="fd432-102">ICorRuntimeHost::GetDefaultDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="fd432-102">ICorRuntimeHost::GetDefaultDomain Method</span></span>
<span data-ttu-id="fd432-103">Ruft einen Schnittstellenzeiger vom Typ <xref:System._AppDomain?displayProperty=nameWithType> , die die Standarddomäne für den aktuellen Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="fd432-103">Gets an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the default domain for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd432-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd432-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd432-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd432-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fd432-106">[out] Einen Schnittstellenzeiger vom Typ <xref:System._AppDomain?displayProperty=nameWithType> auf die <xref:System.AppDomain> -Instanz, die Standardanwendungsdomäne für den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="fd432-106">[out] An interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType> to the <xref:System.AppDomain> instance that represents the default application domain for the process.</span></span>  
  
 <span data-ttu-id="fd432-107">Dieser Zeiger wird als `IUnknown`, sodass Aufrufer, in der Regel aufrufen müssen `QueryInterface` einen Schnittstellenzeiger vom Typ abrufen <xref:System._AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd432-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain an interface pointer of type <xref:System._AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd432-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fd432-108">Return Value</span></span>  
  
|<span data-ttu-id="fd432-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fd432-109">HRESULT</span></span>|<span data-ttu-id="fd432-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd432-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fd432-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fd432-111">S_OK</span></span>|<span data-ttu-id="fd432-112">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="fd432-112">The operation was successful.</span></span>|  
|<span data-ttu-id="fd432-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fd432-113">S_FALSE</span></span>|<span data-ttu-id="fd432-114">Der Vorgang konnte nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fd432-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="fd432-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fd432-115">E_FAIL</span></span>|<span data-ttu-id="fd432-116">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fd432-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="fd432-117">Wenn eine Methode E_FAIL zurückgegeben wird, ist die common Language Runtime (CLR) nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fd432-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="fd432-118">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="fd432-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fd432-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fd432-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fd432-120">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="fd432-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fd432-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd432-121">Requirements</span></span>  
 <span data-ttu-id="fd432-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd432-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd432-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fd432-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd432-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fd432-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd432-125">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="fd432-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd432-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd432-126">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="fd432-127">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd432-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
