---
title: ICLRRuntimeInfo::IsLoaded-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
ms.openlocfilehash: 66ae74deba9ceab9d1ea6b2c0b96a87bf44f32ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714925"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="b4568-102">ICLRRuntimeInfo::IsLoaded-Methode</span><span class="sxs-lookup"><span data-stu-id="b4568-102">ICLRRuntimeInfo::IsLoaded Method</span></span>

<span data-ttu-id="b4568-103">Gibt an, ob die der [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle zugeordnete Common Language Runtime (CLR) in einen Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="b4568-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="b4568-104">Eine Laufzeit kann geladen werden, ohne dass Sie auch gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b4568-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4568-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4568-105">Syntax</span></span>  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4568-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4568-106">Parameters</span></span>  

 `hndProcess`  
 <span data-ttu-id="b4568-107">in Ein Handle für den Prozess.</span><span class="sxs-lookup"><span data-stu-id="b4568-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="b4568-108">[out] `true` , wenn die CLR in den Prozess geladen wird. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="b4568-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4568-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b4568-109">Return Value</span></span>  

 <span data-ttu-id="b4568-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b4568-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b4568-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4568-111">HRESULT</span></span>|<span data-ttu-id="b4568-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b4568-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4568-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4568-113">S_OK</span></span>|<span data-ttu-id="b4568-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b4568-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="b4568-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b4568-115">E_POINTER</span></span>|<span data-ttu-id="b4568-116">`pbLoaded` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="b4568-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4568-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4568-117">Remarks</span></span>  

 <span data-ttu-id="b4568-118">Diese Methode ist abwärts kompatibel mit den folgenden Funktionen und Schnittstellen:</span><span class="sxs-lookup"><span data-stu-id="b4568-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="b4568-119">[ICorRuntimeHost](icorruntimehost-interface.md) -Schnittstelle (in der .NET Framework, Version 1-Hosting-API).</span><span class="sxs-lookup"><span data-stu-id="b4568-119">[ICorRuntimeHost](icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="b4568-120">[ICLRRuntimeHost](iclrruntimehost-interface.md) -Schnittstelle (in der .NET Framework 2,0-Hosting-API).</span><span class="sxs-lookup"><span data-stu-id="b4568-120">[ICLRRuntimeHost](iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="b4568-121">Als veraltet markierte `CorBindTo*` Funktionen (siehe [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md) in der .NET Framework 2,0-Hosting-API).</span><span class="sxs-lookup"><span data-stu-id="b4568-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="b4568-122">Ein Host kann eine der veralteten `CorBindTo*` Funktionen aufrufen, z. b. die [CorBindToRuntime](corbindtoruntime-function.md) -Funktion, um eine bestimmte Version der CLR zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="b4568-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="b4568-123">Der Host kann dann die [ICLRMetaHost:: GetRuntime](iclrmetahost-getruntime-method.md) -Methode aufzurufen und die gleiche Versionsnummer angeben, um eine [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b4568-123">The host could then call the [ICLRMetaHost::GetRuntime](iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="b4568-124">Wenn der Host die- `IsLoaded` Methode auf der zurückgegebenen [iclrruntimeingefo](iclrruntimeinfo-interface.md) -Schnittstelle aufruft, `pbLoaded` gibt zurück, `true` andernfalls wird zurückgegeben `false` .</span><span class="sxs-lookup"><span data-stu-id="b4568-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4568-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b4568-125">Requirements</span></span>  

 <span data-ttu-id="b4568-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4568-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4568-127">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="b4568-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b4568-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b4568-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4568-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4568-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4568-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4568-130">See also</span></span>

- [<span data-ttu-id="b4568-131">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4568-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="b4568-132">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b4568-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="b4568-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="b4568-133">Hosting</span></span>](index.md)
