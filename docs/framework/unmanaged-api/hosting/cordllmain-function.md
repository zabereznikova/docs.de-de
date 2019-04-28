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
ms.openlocfilehash: c509f475d5bf0105ece9791ee3e51d21c298a31f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666920"
---
# <a name="cordllmain-function"></a><span data-ttu-id="23d79-102">\_CorDllMain-Funktion</span><span class="sxs-lookup"><span data-stu-id="23d79-102">\_CorDllMain Function</span></span>

<span data-ttu-id="23d79-103">Initialisiert die common Language Runtime (CLR), sucht den verwalteten Einstiegspunkt im CLR-Header der DLL-Assembly und startet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="23d79-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d79-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23d79-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23d79-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23d79-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="23d79-106">[in] Der Instanzhandle des geladenen Moduls.</span><span class="sxs-lookup"><span data-stu-id="23d79-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="23d79-107">[in] Gibt an, warum die DLL-Einstiegspunkt-Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="23d79-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="23d79-108">Dieser Parameter kann einen der folgenden Werte sein: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span><span class="sxs-lookup"><span data-stu-id="23d79-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="23d79-109">Beschreibungen dieser Werte finden Sie die `DllMain` Dokumentation im Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="23d79-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="23d79-110">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="23d79-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23d79-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="23d79-111">Return Value</span></span>  
 <span data-ttu-id="23d79-112">Diese Methode gibt `true` für Erfolg und `false` Wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="23d79-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23d79-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23d79-113">Remarks</span></span>  
 <span data-ttu-id="23d79-114">Diese Funktion wird vom Ladeprogramm Betriebssystems für DLL-Assemblys aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="23d79-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="23d79-115">Für ausführbare Assemblys ruft das Ladeprogramm die [ \_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) stattdessen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="23d79-115">For executable assemblies, the loader calls the [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="23d79-116">Vom Ladeprogramm des Betriebssystems ruft diese Methode unabhängig von der Einstiegspunkt in die DLL-Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="23d79-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="23d79-117">Die `_CorDllMain` Funktion direkt vom Ladeprogramm Betriebssystems aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="23d79-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="23d79-118">Weitere Informationen finden Sie im Abschnitt "Hinweise" in der [ \_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="23d79-118">For additional information, see the Remarks section in the [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23d79-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23d79-119">Requirements</span></span>  

 <span data-ttu-id="23d79-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23d79-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23d79-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="23d79-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23d79-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="23d79-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="23d79-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23d79-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d79-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23d79-124">See also</span></span>

- [<span data-ttu-id="23d79-125">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="23d79-125">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
