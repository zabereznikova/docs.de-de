---
title: _CorDllMain-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorDllMain
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorDllMain
helpviewer_keywords: _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 985f2284026054217671de767c316b1fba35c098
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="cordllmain-function"></a><span data-ttu-id="85f80-102">_CorDllMain-Funktion</span><span class="sxs-lookup"><span data-stu-id="85f80-102">_CorDllMain Function</span></span>
<span data-ttu-id="85f80-103">Initialisiert die common Language Runtime (CLR), sucht den verwalteten Einstiegspunkt im CLR-Header der DLL-Assembly und startet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="85f80-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85f80-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85f80-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85f80-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="85f80-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="85f80-106">[in] Der Instanzhandle des geladenen Moduls.</span><span class="sxs-lookup"><span data-stu-id="85f80-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="85f80-107">[in] Gibt an, warum die DLL-Einstiegspunkt-Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="85f80-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="85f80-108">Dieser Parameter kann einen der folgenden Werte sein: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH oder DLL_PROCESS_DETACH.</span><span class="sxs-lookup"><span data-stu-id="85f80-108">This parameter can be one of the following values: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, or DLL_PROCESS_DETACH.</span></span> <span data-ttu-id="85f80-109">Eine Beschreibung dieser Werte finden Sie unter der `DllMain` Dokumentation im Plattform-SDK.</span><span class="sxs-lookup"><span data-stu-id="85f80-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="85f80-110">[in] Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="85f80-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85f80-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="85f80-111">Return Value</span></span>  
 <span data-ttu-id="85f80-112">Diese Methode gibt `true` für Erfolg und `false` , wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="85f80-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85f80-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85f80-113">Remarks</span></span>  
 <span data-ttu-id="85f80-114">Diese Funktion wird für DLL-Assemblys durch das Betriebssystemladeprogramm aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="85f80-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="85f80-115">Für ausführbare Assemblys ruft das Ladeprogramm die [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) stattdessen-Funktion.</span><span class="sxs-lookup"><span data-stu-id="85f80-115">For executable assemblies, the loader calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="85f80-116">Vom Ladeprogramm des Betriebssystems ruft diese Methode unabhängig von den Einstiegspunkt in die DLL-Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="85f80-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
 <span data-ttu-id="85f80-117">In Windows 98, Windows ME, Windows NT und Windows 2000 die `_CorDllMain` Funktion wird aufgerufen, indirekt über eine Fixupin vom Ladeprogramm des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="85f80-117">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorDllMain` function is called indirectly through a fixupin the operating system loader.</span></span> <span data-ttu-id="85f80-118">In allen anderen Versionen von Windows wird er direkt vom Ladeprogramm Betriebssystems aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="85f80-118">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="85f80-119">Weitere Informationen finden Sie im Abschnitt "Hinweise" in der [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="85f80-119">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85f80-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="85f80-120">Requirements</span></span>  
 <span data-ttu-id="85f80-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85f80-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85f80-122">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="85f80-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85f80-123">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="85f80-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85f80-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85f80-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85f80-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85f80-125">See Also</span></span>  
 [<span data-ttu-id="85f80-126">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="85f80-126">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
