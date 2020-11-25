---
title: LockClrVersion-Funktion
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
ms.openlocfilehash: 2ff08ec8f194ccc9e968b3a7ee017afe788f4b03
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704928"
---
# <a name="lockclrversion-function"></a><span data-ttu-id="d13c4-102">LockClrVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="d13c4-102">LockClrVersion Function</span></span>

<span data-ttu-id="d13c4-103">Ermöglicht dem Host, zu bestimmen, welche Version des Common Language Runtime (CLR) innerhalb des Prozesses verwendet werden soll, bevor die CLR explizit initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d13c4-103">Allows the host to determine which version of the common language runtime (CLR) will be used within the process before explicitly initializing the CLR.</span></span>  
  
 <span data-ttu-id="d13c4-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="d13c4-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d13c4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d13c4-105">Syntax</span></span>  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d13c4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d13c4-106">Parameters</span></span>  

 `hostCallback`  
 <span data-ttu-id="d13c4-107">in Die Funktion, die von der CLR bei der Initialisierung aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="d13c4-107">[in] The function to be called by the CLR upon initialization.</span></span>  
  
 `pBeginHostSetup`  
 <span data-ttu-id="d13c4-108">in Die Funktion, die vom Host aufgerufen werden soll, um die CLR darüber zu informieren, dass die Initialisierung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="d13c4-108">[in] The function to be called by the host to inform the CLR that initialization is starting.</span></span>  
  
 `pEndHostSetup`  
 <span data-ttu-id="d13c4-109">in Die Funktion, die vom Host aufgerufen werden soll, um die CLR darüber zu informieren, dass die Initialisierung beendet ist.</span><span class="sxs-lookup"><span data-stu-id="d13c4-109">[in] The function to be called by the host to inform the CLR that initialization is complete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d13c4-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d13c4-110">Return Value</span></span>  

 <span data-ttu-id="d13c4-111">Diese Methode gibt neben den folgenden Werten Standard-COM-Fehlercodes zurück, die in WinError. h definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d13c4-111">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="d13c4-112">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="d13c4-112">Return code</span></span>|<span data-ttu-id="d13c4-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d13c4-113">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d13c4-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d13c4-114">S_OK</span></span>|<span data-ttu-id="d13c4-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d13c4-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="d13c4-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d13c4-116">E_INVALIDARG</span></span>|<span data-ttu-id="d13c4-117">Mindestens eines der Argumente ist NULL.</span><span class="sxs-lookup"><span data-stu-id="d13c4-117">One or more of the arguments is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d13c4-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d13c4-118">Remarks</span></span>  

 <span data-ttu-id="d13c4-119">Der Host ruft auf, `LockClrVersion` bevor die CLR initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d13c4-119">The host calls `LockClrVersion` before initializing the CLR.</span></span> <span data-ttu-id="d13c4-120">`LockClrVersion` erfordert drei Parameter, von denen alle Rückrufe des Typs [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md)sind.</span><span class="sxs-lookup"><span data-stu-id="d13c4-120">`LockClrVersion` takes three parameters, all of which are callbacks of type [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md).</span></span> <span data-ttu-id="d13c4-121">Dieser Typ wird wie folgt definiert.</span><span class="sxs-lookup"><span data-stu-id="d13c4-121">This type is defined as follows.</span></span>  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 <span data-ttu-id="d13c4-122">Die folgenden Schritte erfolgen bei der Initialisierung der Laufzeit:</span><span class="sxs-lookup"><span data-stu-id="d13c4-122">The following steps occur upon initialization of the runtime:</span></span>  
  
1. <span data-ttu-id="d13c4-123">Der Host ruft [CorBindToRuntimeEx](corbindtoruntimeex-function.md) oder eine der anderen Lauf Zeit Initialisierungs Funktionen auf.</span><span class="sxs-lookup"><span data-stu-id="d13c4-123">The host calls [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or one of the other runtime initialization functions.</span></span> <span data-ttu-id="d13c4-124">Alternativ kann der Host die Laufzeit mithilfe der COM-Objekt Aktivierung initialisieren.</span><span class="sxs-lookup"><span data-stu-id="d13c4-124">Alternatively, the host could initialize the runtime using COM object activation.</span></span>  
  
2. <span data-ttu-id="d13c4-125">Die Laufzeit ruft die durch den-Parameter angegebene Funktion auf `hostCallback` .</span><span class="sxs-lookup"><span data-stu-id="d13c4-125">The runtime calls the function specified by the `hostCallback` parameter.</span></span>  
  
3. <span data-ttu-id="d13c4-126">Die von angegebene Funktion `hostCallback` führt dann die folgende Sequenz von Aufrufen aus:</span><span class="sxs-lookup"><span data-stu-id="d13c4-126">The function specified by `hostCallback` then makes the following sequence of calls:</span></span>  
  
    - <span data-ttu-id="d13c4-127">Die Funktion, die durch den-Parameter angegeben wird `pBeginHostSetup` .</span><span class="sxs-lookup"><span data-stu-id="d13c4-127">The function specified by the `pBeginHostSetup` parameter.</span></span>  
  
    - <span data-ttu-id="d13c4-128">`CorBindToRuntimeEx` (oder eine andere Lauf Zeit Initialisierungsfunktion).</span><span class="sxs-lookup"><span data-stu-id="d13c4-128">`CorBindToRuntimeEx` (or another runtime initialization function).</span></span>  
  
    - <span data-ttu-id="d13c4-129">[ICLRRuntimeHost:: abgelegte Control](iclrruntimehost-sethostcontrol-method.md).</span><span class="sxs-lookup"><span data-stu-id="d13c4-129">[ICLRRuntimeHost::SetHostControl](iclrruntimehost-sethostcontrol-method.md).</span></span>  
  
    - <span data-ttu-id="d13c4-130">[ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="d13c4-130">[ICLRRuntimeHost::Start](iclrruntimehost-start-method.md).</span></span>  
  
    - <span data-ttu-id="d13c4-131">Die Funktion, die durch den-Parameter angegeben wird `pEndHostSetup` .</span><span class="sxs-lookup"><span data-stu-id="d13c4-131">The function specified by the `pEndHostSetup` parameter.</span></span>  
  
 <span data-ttu-id="d13c4-132">Alle Aufrufe von `pBeginHostSetup` bis `pEndHostSetup` müssen in einem einzelnen Thread oder einer Fiber mit demselben logischen Stapel erfolgen.</span><span class="sxs-lookup"><span data-stu-id="d13c4-132">All the calls from `pBeginHostSetup` to `pEndHostSetup` must occur on a single thread or fiber, with the same logical stack.</span></span> <span data-ttu-id="d13c4-133">Dieser Thread kann sich von dem Thread unterscheiden, bei dem `hostCallback` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d13c4-133">This thread can be different from the thread upon which `hostCallback` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d13c4-134">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d13c4-134">Requirements</span></span>  

 <span data-ttu-id="d13c4-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d13c4-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d13c4-136">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d13c4-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d13c4-137">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d13c4-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d13c4-138">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d13c4-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d13c4-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d13c4-139">See also</span></span>

- [<span data-ttu-id="d13c4-140">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="d13c4-140">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
