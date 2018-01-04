---
title: LoadLibraryShim-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: LoadLibraryShim
helpviewer_keywords: LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5b8fe8413d0eff332e60508a083f03574e58d7bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="278b8-102">LoadLibraryShim-Funktion</span><span class="sxs-lookup"><span data-stu-id="278b8-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="278b8-103">Lädt die angegebene Version einer DLL, die in das verteilbare .NET Framework-Paket enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="278b8-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="278b8-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="278b8-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="278b8-105">Verwenden der [ICLRRuntimeInfo:: LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="278b8-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="278b8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="278b8-106">Syntax</span></span>  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="278b8-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="278b8-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="278b8-108">[in] Eine NULL-terminierte Zeichenfolge mit dem Namen der DLL aus dem .NET Framework-Klassenbibliothek geladen werden.</span><span class="sxs-lookup"><span data-stu-id="278b8-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="278b8-109">[in] Eine NULL-terminierte Zeichenfolge, die die Version der DLL zu ladende darstellt.</span><span class="sxs-lookup"><span data-stu-id="278b8-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="278b8-110">Wenn `szVersion` null ist, ist die Version, die für die ausgewählte laden die neueste Version der angegebenen DLL, die kleiner als der Version 4 ist.</span><span class="sxs-lookup"><span data-stu-id="278b8-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="278b8-111">D. h., alle Versionen gleich oder größer als der Version 4 werden ignoriert, wenn `szVersion` null ist, und wenn keine Version kleiner als 4-Version installiert ist, kann die DLL zu laden.</span><span class="sxs-lookup"><span data-stu-id="278b8-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="278b8-112">Wird verwendet, um diese Installation sicher, dass die [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] hat keine Auswirkungen auf bereits vorhandene Anwendungen oder Komponenten.</span><span class="sxs-lookup"><span data-stu-id="278b8-112">This is to ensure that installation of the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] does not affect pre-existing applications or components.</span></span> <span data-ttu-id="278b8-113">Finden Sie im Eintrag [prozessinterne SxS und Migration Schnellstart](http://go.microsoft.com/fwlink/?LinkId=200329) im CLR-Teamblog.</span><span class="sxs-lookup"><span data-stu-id="278b8-113">See the entry [In-Proc SxS and Migration Quick Start](http://go.microsoft.com/fwlink/?LinkId=200329) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="278b8-114">Für zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="278b8-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="278b8-115">[out] Ein Zeiger auf das Handle des Moduls.</span><span class="sxs-lookup"><span data-stu-id="278b8-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="278b8-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="278b8-116">Return Value</span></span>  
 <span data-ttu-id="278b8-117">Diese Methode gibt Component Object Model (COM) Standardfehlercodes in WinError.h definiert, zusätzlich zu den folgenden Werten zurück.</span><span class="sxs-lookup"><span data-stu-id="278b8-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="278b8-118">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="278b8-118">Return code</span></span>|<span data-ttu-id="278b8-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="278b8-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="278b8-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="278b8-120">S_OK</span></span>|<span data-ttu-id="278b8-121">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="278b8-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="278b8-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="278b8-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="278b8-123">Laden von `szDllName` erfordert laden, die die common Language Runtime (CLR) und die erforderliche Version der CLR kann nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="278b8-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="278b8-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="278b8-124">Remarks</span></span>  
 <span data-ttu-id="278b8-125">Diese Funktion dient zum Laden von DLLs, die in das verteilbare .NET Framework-Paket enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="278b8-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="278b8-126">Es wird nicht vom Benutzer generierte DLLs geladen.</span><span class="sxs-lookup"><span data-stu-id="278b8-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="278b8-127">Ab .NET Framework, Version 2.0, bewirkt das Laden von Fusion.dll die CLR geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="278b8-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="278b8-128">Dies ist, da die Funktionen in Fusion.dll jetzt Wrapper sind, deren Implementierung von der Runtime bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="278b8-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="278b8-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="278b8-129">Requirements</span></span>  
 <span data-ttu-id="278b8-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="278b8-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="278b8-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="278b8-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="278b8-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="278b8-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="278b8-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="278b8-133">See Also</span></span>  
 [<span data-ttu-id="278b8-134">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="278b8-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
