---
title: _CorDllMain-Funktion
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f62ad2c9ec6e1c9672ac5c78e838e926b02359f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512371"
---
# <a name="cordllmain-function"></a><span data-ttu-id="67e69-102">_CorDllMain-Funktion</span><span class="sxs-lookup"><span data-stu-id="67e69-102">_CorDllMain Function</span></span>
<span data-ttu-id="67e69-103">Initialisiert die common Language Runtime (CLR), sucht den verwalteten Einstiegspunkt im CLR-Header der DLL-Assembly und startet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="67e69-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e69-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67e69-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67e69-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67e69-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="67e69-106">[in] Der Instanzhandle des geladenen Moduls.</span><span class="sxs-lookup"><span data-stu-id="67e69-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="67e69-107">[in] Gibt an, warum die DLL-Einstiegspunkt-Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="67e69-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="67e69-108">Dieser Parameter kann einen der folgenden Werte sein: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, or DLL_PROCESS_DETACH.</span><span class="sxs-lookup"><span data-stu-id="67e69-108">This parameter can be one of the following values: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, or DLL_PROCESS_DETACH.</span></span> <span data-ttu-id="67e69-109">Beschreibungen dieser Werte finden Sie die `DllMain` Dokumentation im Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="67e69-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="67e69-110">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="67e69-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67e69-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="67e69-111">Return Value</span></span>  
 <span data-ttu-id="67e69-112">Diese Methode gibt `true` für Erfolg und `false` Wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="67e69-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67e69-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67e69-113">Remarks</span></span>  
 <span data-ttu-id="67e69-114">Diese Funktion wird vom Ladeprogramm Betriebssystems für DLL-Assemblys aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="67e69-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="67e69-115">Für ausführbare Assemblys ruft das Ladeprogramm die [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) stattdessen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="67e69-115">For executable assemblies, the loader calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="67e69-116">Vom Ladeprogramm des Betriebssystems ruft diese Methode unabhängig von der Einstiegspunkt in die DLL-Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="67e69-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
 <span data-ttu-id="67e69-117">In Windows 98, Windows ME, Windows NT und Windows 2000 die `_CorDllMain` Funktion wird aufgerufen, indirekt über eine Fixupin vom Ladeprogramm des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="67e69-117">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorDllMain` function is called indirectly through a fixupin the operating system loader.</span></span> <span data-ttu-id="67e69-118">In allen anderen Versionen von Windows spricht man direkt vom Ladeprogramm Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="67e69-118">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="67e69-119">Weitere Informationen finden Sie im Abschnitt "Hinweise" in der [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="67e69-119">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67e69-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67e69-120">Requirements</span></span>  
 <span data-ttu-id="67e69-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67e69-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67e69-122">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="67e69-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="67e69-123">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="67e69-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="67e69-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67e69-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e69-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67e69-125">See also</span></span>
- [<span data-ttu-id="67e69-126">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="67e69-126">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
