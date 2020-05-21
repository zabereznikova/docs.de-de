---
title: ICorRuntimeHost::CurrentDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
ms.openlocfilehash: 558b6e4c6ac369e33be3d45b7241e8b11db8bfae
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760393"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="8b4ff-102">ICorRuntimeHost::CurrentDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="8b4ff-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="8b4ff-103">Entlädt die angegebene Anwendungsdomäne aus dem aktuellen Prozess.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b4ff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b4ff-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b4ff-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b4ff-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="8b4ff-106">in Ein Zeiger vom Typ <xref:System._AppDomain?displayProperty=nameWithType> , der die zu entladende Domäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b4ff-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8b4ff-107">Return Value</span></span>  
  
|<span data-ttu-id="8b4ff-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b4ff-108">HRESULT</span></span>|<span data-ttu-id="8b4ff-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8b4ff-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b4ff-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b4ff-110">S_OK</span></span>|<span data-ttu-id="8b4ff-111">Der Vorgang wurde durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-111">The operation was successful.</span></span>|  
|<span data-ttu-id="8b4ff-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8b4ff-112">S_FALSE</span></span>|<span data-ttu-id="8b4ff-113">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="8b4ff-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8b4ff-114">E_FAIL</span></span>|<span data-ttu-id="8b4ff-115">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="8b4ff-116">Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="8b4ff-117">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8b4ff-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8b4ff-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8b4ff-119">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="8b4ff-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b4ff-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8b4ff-120">Requirements</span></span>  
 <span data-ttu-id="8b4ff-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b4ff-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b4ff-122">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8b4ff-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b4ff-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8b4ff-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b4ff-124">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="8b4ff-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b4ff-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8b4ff-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="8b4ff-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b4ff-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
