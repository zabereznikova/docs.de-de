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
ms.openlocfilehash: 1b3ebcabc66ee7ca29245bb02d958be311bc65fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673695"
---
# <a name="_cordllmain-function"></a><span data-ttu-id="c3423-102">\_Cordllmain-Funktion</span><span class="sxs-lookup"><span data-stu-id="c3423-102">\_CorDllMain Function</span></span>

<span data-ttu-id="c3423-103">Initialisiert die Common Language Runtime (CLR), gibt den verwalteten Einstiegspunkt im CLR-Header der dll-Assembly an und beginnt die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="c3423-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3423-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3423-104">Syntax</span></span>  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3423-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c3423-105">Parameters</span></span>  

 `hInst`  
 <span data-ttu-id="c3423-106">in Der Instanzhandle des geladenen Moduls.</span><span class="sxs-lookup"><span data-stu-id="c3423-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="c3423-107">in Gibt an, warum die DLL-Einstiegspunkt Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c3423-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="c3423-108">Dieser Parameter kann einen der folgenden Werte aufweisen: DLL- \_ PROCESS_ATTACH, DLL- \_ Thread \_ Anfügen, Anfügen von DLL- \_ Threads \_ oder Trennen von DLL- \_ Prozessen \_ .</span><span class="sxs-lookup"><span data-stu-id="c3423-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="c3423-109">Beschreibungen dieser Werte finden Sie `DllMain` in der Dokumentation im Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="c3423-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="c3423-110">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c3423-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3423-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c3423-111">Return Value</span></span>  

 <span data-ttu-id="c3423-112">Diese Methode gibt `true` für Erfolg und `false` bei Auftreten eines Fehlers zurück.</span><span class="sxs-lookup"><span data-stu-id="c3423-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3423-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c3423-113">Remarks</span></span>  

 <span data-ttu-id="c3423-114">Diese Funktion wird vom Betriebssystem-Lade Modul für dll-Assemblys aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c3423-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="c3423-115">Bei ausführbaren Assemblys Ruft das Lade Programm stattdessen die [ \_ CORExeMain](corexemain-function.md) -Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="c3423-115">For executable assemblies, the loader calls the [\_CorExeMain](corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="c3423-116">Das Betriebssystem-Lade Modul ruft diese Methode unabhängig vom Einstiegspunkt auf, der in der DLL-Datei angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c3423-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="c3423-117">Die- `_CorDllMain` Funktion wird direkt vom Betriebssystem-Lade Modul aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="c3423-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="c3423-118">Weitere Informationen finden Sie im Abschnitt "Hinweise" im Thema [ \_ CorValidateImage](corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="c3423-118">For additional information, see the Remarks section in the [\_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3423-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c3423-119">Requirements</span></span>  

 <span data-ttu-id="c3423-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3423-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3423-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c3423-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c3423-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c3423-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3423-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3423-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3423-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3423-124">See also</span></span>

- [<span data-ttu-id="c3423-125">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="c3423-125">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
