---
title: ICLRRuntimeInfo::LoadLibrary-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
ms.openlocfilehash: 09c80c3a56d86943ebe00e5222bb5452ab44e150
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762174"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="7874e-102">ICLRRuntimeInfo::LoadLibrary-Methode</span><span class="sxs-lookup"><span data-stu-id="7874e-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="7874e-103">Lädt eine .NET Framework Bibliothek aus der Common Language Runtime (CLR), die durch eine [iclrruntimeingefo](iclrruntimeinfo-interface.md) -Schnittstelle dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7874e-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="7874e-104">Diese Methode löst die [LoadLibraryShim](loadlibraryshim-function.md) -Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="7874e-104">This method supersedes the [LoadLibraryShim](loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7874e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7874e-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7874e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7874e-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="7874e-107">in Der Name der Assembly, die geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="7874e-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="7874e-108">vorgenommen Ein Handle für die geladene Assembly.</span><span class="sxs-lookup"><span data-stu-id="7874e-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7874e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7874e-109">Return Value</span></span>  
 <span data-ttu-id="7874e-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7874e-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7874e-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7874e-111">HRESULT</span></span>|<span data-ttu-id="7874e-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7874e-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7874e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="7874e-113">S_OK</span></span>|<span data-ttu-id="7874e-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7874e-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="7874e-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="7874e-115">E_POINTER</span></span>|<span data-ttu-id="7874e-116">`pwzDllName` oder `phndModule` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="7874e-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="7874e-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7874e-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7874e-118">Es ist nicht genügend Arbeitsspeicher verfügbar, um die Anforderung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7874e-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7874e-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7874e-119">Remarks</span></span>  
 <span data-ttu-id="7874e-120">Diese Methode lädt nur DLLs, die in der .NET Framework verteilbaren Pakets enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="7874e-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="7874e-121">Benutzergenerierte Assemblys können nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="7874e-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7874e-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7874e-122">Requirements</span></span>  
 <span data-ttu-id="7874e-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7874e-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7874e-124">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="7874e-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7874e-125">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7874e-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7874e-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7874e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7874e-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7874e-127">See also</span></span>

- [<span data-ttu-id="7874e-128">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7874e-128">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="7874e-129">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7874e-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="7874e-130">Hosting</span><span class="sxs-lookup"><span data-stu-id="7874e-130">Hosting</span></span>](index.md)
