---
title: ICorRuntimeHost::CreateDomainSetup-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: 1be7eee5c2591f26c33572446080a4fa4b3b929d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723895"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="6f5c6-102">ICorRuntimeHost::CreateDomainSetup-Methode</span><span class="sxs-lookup"><span data-stu-id="6f5c6-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>

<span data-ttu-id="6f5c6-103">Ruft einen Schnittstellen Zeiger vom Typ IAppDomainSetup auf eine- <xref:System.AppDomainSetup?displayProperty=nameWithType> Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="6f5c6-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="6f5c6-104">`IAppDomainSetup` stellt Methoden bereit, um Aspekte einer Anwendungsdomäne vor der Erstellung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6f5c6-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f5c6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f5c6-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f5c6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f5c6-106">Parameters</span></span>  

 `pAppDomainSetup`  
 <span data-ttu-id="6f5c6-107">vorgenommen Ein Schnittstellen Zeiger auf eine- <xref:System.AppDomainSetup?displayProperty=nameWithType> Instanz.</span><span class="sxs-lookup"><span data-stu-id="6f5c6-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="6f5c6-108">Dieser Parameter ist als typisiert `IUnknown` , sodass Aufrufer in der Regel `QueryInterface` für diesen Zeiger aufrufen, um einen Schnittstellen Zeiger vom Typ zu erhalten `IAppDomainSetup` .</span><span class="sxs-lookup"><span data-stu-id="6f5c6-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f5c6-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6f5c6-109">Return Value</span></span>  
  
|<span data-ttu-id="6f5c6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f5c6-110">HRESULT</span></span>|<span data-ttu-id="6f5c6-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6f5c6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f5c6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f5c6-112">S_OK</span></span>|<span data-ttu-id="6f5c6-113">Der Vorgang wurde durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="6f5c6-113">The operation was successful.</span></span>|  
|<span data-ttu-id="6f5c6-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6f5c6-114">S_FALSE</span></span>|<span data-ttu-id="6f5c6-115">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6f5c6-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="6f5c6-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6f5c6-116">E_FAIL</span></span>|<span data-ttu-id="6f5c6-117">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6f5c6-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="6f5c6-118">Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="6f5c6-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="6f5c6-119">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="6f5c6-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6f5c6-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6f5c6-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6f5c6-121">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="6f5c6-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f5c6-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f5c6-122">Remarks</span></span>  

 <span data-ttu-id="6f5c6-123">Der von dieser Methode zurückgegebene Zeiger wird in der Regel als Parameter an die Methode " [kreatedomainex](icorruntimehost-createdomainex-method.md) " übergeben.</span><span class="sxs-lookup"><span data-stu-id="6f5c6-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f5c6-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6f5c6-124">Requirements</span></span>  

 <span data-ttu-id="6f5c6-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f5c6-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f5c6-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="6f5c6-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f5c6-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6f5c6-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f5c6-128">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="6f5c6-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5c6-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f5c6-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="6f5c6-130">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f5c6-130">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
