---
title: ICorRuntimeHost::CreateEvidence-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
ms.openlocfilehash: 6627fce519934177aefd26a612e5b00ca1941d02
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715666"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="21c05-102">ICorRuntimeHost::CreateEvidence-Methode</span><span class="sxs-lookup"><span data-stu-id="21c05-102">ICorRuntimeHost::CreateEvidence Method</span></span>

<span data-ttu-id="21c05-103">Ruft einen Schnittstellen Zeiger vom Typ ab <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> , mit dem der Host Sicherheits Beweise erstellen kann, die an die Methode " [kreatedomain](icorruntimehost-createdomain-method.md) " oder " [kreatedomainex](icorruntimehost-createdomainex-method.md) " übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="21c05-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](icorruntimehost-createdomain-method.md) or [CreateDomainEx](icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21c05-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21c05-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21c05-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="21c05-105">Parameters</span></span>  

 `pEvidence`  
 <span data-ttu-id="21c05-106">vorgenommen Ein Schnittstellen Zeiger auf eine- <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> Instanz, mit der Sicherheits Beweise erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="21c05-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="21c05-107">Dieser Zeiger ist typisiert `IUnknown` , sodass Aufrufer in der Regel `QueryInterface` für diese Schnittstelle aufgerufen werden, um einen Zeiger auf eine zu erhalten <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="21c05-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21c05-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="21c05-108">Return Value</span></span>  
  
|<span data-ttu-id="21c05-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="21c05-109">HRESULT</span></span>|<span data-ttu-id="21c05-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="21c05-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="21c05-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="21c05-111">S_OK</span></span>|<span data-ttu-id="21c05-112">Der Vorgang wurde durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="21c05-112">The operation was successful.</span></span>|  
|<span data-ttu-id="21c05-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="21c05-113">S_FALSE</span></span>|<span data-ttu-id="21c05-114">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="21c05-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="21c05-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="21c05-115">E_FAIL</span></span>|<span data-ttu-id="21c05-116">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="21c05-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="21c05-117">Wenn eine Methode E_FAIL zurückgibt, ist die Common Language Runtime (CLR) im Prozess nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="21c05-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="21c05-118">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="21c05-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="21c05-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="21c05-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="21c05-120">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="21c05-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21c05-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21c05-121">Remarks</span></span>  

 <span data-ttu-id="21c05-122">Diese Methode gibt eine leere Auflistung zurück, die nicht aus nativem Code aufgefüllt werden kann.</span><span class="sxs-lookup"><span data-stu-id="21c05-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="21c05-123">Verwenden Sie stattdessen die- <xref:System.Security.Policy.Evidence> Methode.</span><span class="sxs-lookup"><span data-stu-id="21c05-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21c05-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="21c05-124">Requirements</span></span>  

 <span data-ttu-id="21c05-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21c05-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21c05-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="21c05-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21c05-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="21c05-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21c05-128">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="21c05-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21c05-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21c05-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="21c05-130">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21c05-130">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
