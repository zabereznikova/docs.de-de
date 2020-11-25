---
title: ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference-Methode
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
ms.openlocfilehash: 263058131e63205aa37f81847ed647944fef7540
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731396"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="c577f-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference-Methode</span><span class="sxs-lookup"><span data-stu-id="c577f-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>

<span data-ttu-id="c577f-103">Ruft einen [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) -Enumerator für die Assemblyidentitäten ab, auf die von der Assembly mit dem angegebenen Identitätstyp verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c577f-103">Gets an [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c577f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c577f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c577f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c577f-105">Parameters</span></span>  

 `dwMachineType`  
 <span data-ttu-id="c577f-106">in Ein gültiger-Wert, der die Prozessorarchitektur angibt, wie in "Winnt. h" definiert.</span><span class="sxs-lookup"><span data-stu-id="c577f-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c577f-107">in Wird für zukünftige Erweiterbarkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c577f-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="c577f-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT ist der einzige Wert, der von der aktuellen Version des Common Language Runtime (CLR) unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="c577f-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="c577f-109">in Eine nicht transparente Assemblybindungsidentität, die in der Regel von einem Aufrufen der [ICLRAssemblyIdentityManager:: GetBindingIdentityFromFile](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) -Methode oder der [ICLRAssemblyIdentityManager:: GetBindingIdentityFromStream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) -Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c577f-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="c577f-110">vorgenommen Ein Schnittstellen Zeiger auf einen `ICLRProbingAssemblyEnum` Enumerator, der Verweise auf die Assemblys enthält, auf die von der durch identifizierten Assembly verwiesen wird `pwzReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="c577f-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c577f-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c577f-111">Return Value</span></span>  
  
|<span data-ttu-id="c577f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c577f-112">HRESULT</span></span>|<span data-ttu-id="c577f-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c577f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c577f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c577f-114">S_OK</span></span>|<span data-ttu-id="c577f-115">Die Methode wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c577f-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="c577f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c577f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c577f-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c577f-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c577f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c577f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c577f-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="c577f-119">The call timed out.</span></span>|  
|<span data-ttu-id="c577f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c577f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c577f-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c577f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c577f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c577f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c577f-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="c577f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c577f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c577f-124">E_FAIL</span></span>|<span data-ttu-id="c577f-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c577f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c577f-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="c577f-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c577f-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c577f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c577f-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c577f-128">Requirements</span></span>  

 <span data-ttu-id="c577f-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c577f-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c577f-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c577f-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c577f-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c577f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c577f-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c577f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c577f-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c577f-133">See also</span></span>

- [<span data-ttu-id="c577f-134">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c577f-134">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c577f-135">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c577f-135">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="c577f-136">ICLRProbingAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c577f-136">ICLRProbingAssemblyEnum Interface</span></span>](iclrprobingassemblyenum-interface.md)
