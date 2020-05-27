---
title: LoadLibraryShim-Funktion
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
ms.openlocfilehash: 4b270c36bdbea9c8d81915eba424cae1054ce7d7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008533"
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="5944a-102">LoadLibraryShim-Funktion</span><span class="sxs-lookup"><span data-stu-id="5944a-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="5944a-103">Lädt eine angegebene Version einer DLL, die im .NET Framework verteilbaren Paket enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="5944a-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="5944a-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="5944a-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="5944a-105">Verwenden Sie stattdessen die [iclrruntimumfo:: LoadLibrary](iclrruntimeinfo-loadlibrary-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="5944a-105">Use the [ICLRRuntimeInfo::LoadLibrary](iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5944a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5944a-106">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5944a-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="5944a-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="5944a-108">in Eine mit NULL endende Zeichenfolge, die den Namen der DLL darstellt, die aus der .NET Framework Bibliothek geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="5944a-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="5944a-109">in Eine mit NULL endende Zeichenfolge, die die Version der zu ladenden DLL darstellt.</span><span class="sxs-lookup"><span data-stu-id="5944a-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="5944a-110">Wenn `szVersion` NULL ist, ist die für das Laden ausgewählte Version die neueste Version der angegebenen DLL, die kleiner als Version 4 ist.</span><span class="sxs-lookup"><span data-stu-id="5944a-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="5944a-111">Das heißt, dass alle Versionen, die gleich oder größer als Version 4 sind, ignoriert werden `szVersion` , wenn NULL ist, und wenn keine Version, die kleiner als Version 4 ist, installiert ist, kann die dll nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="5944a-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="5944a-112">Dadurch wird sichergestellt, dass die Installation des .NET Framework 4 keine Auswirkungen auf bereits vorhandene Anwendungen oder Komponenten hat.</span><span class="sxs-lookup"><span data-stu-id="5944a-112">This is to ensure that installation of the .NET Framework 4 does not affect pre-existing applications or components.</span></span> <span data-ttu-id="5944a-113">Weitere Informationen finden Sie im Blogbeitrag [in-Proc SxS and Migration Schnellstart](https://devblogs.microsoft.com/dotnet/in-proc-sxs-and-migration-quick-start/) im CLR-Teamblog.</span><span class="sxs-lookup"><span data-stu-id="5944a-113">See the entry [In-Proc SxS and Migration Quick Start](https://devblogs.microsoft.com/dotnet/in-proc-sxs-and-migration-quick-start/) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="5944a-114">Für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="5944a-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="5944a-115">vorgenommen Ein Zeiger auf das Handle des Moduls.</span><span class="sxs-lookup"><span data-stu-id="5944a-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5944a-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5944a-116">Return Value</span></span>  
 <span data-ttu-id="5944a-117">Diese Methode gibt zusätzlich zu den folgenden Werten in WinError. h definierte Standard-Component Object Model (com)-Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="5944a-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="5944a-118">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="5944a-118">Return code</span></span>|<span data-ttu-id="5944a-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5944a-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5944a-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="5944a-120">S_OK</span></span>|<span data-ttu-id="5944a-121">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5944a-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="5944a-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="5944a-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="5944a-123">Das Laden `szDllName` erfordert das Laden der Common Language Runtime (CLR), und die erforderliche Version der CLR kann nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="5944a-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5944a-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5944a-124">Remarks</span></span>  
 <span data-ttu-id="5944a-125">Diese Funktion wird zum Laden von DLLs verwendet, die in der .NET Framework verteilbaren Pakets enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5944a-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="5944a-126">Benutzergenerierte DLLs werden nicht geladen.</span><span class="sxs-lookup"><span data-stu-id="5944a-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5944a-127">Beginnend mit der .NET Framework Version 2,0 bewirkt das Laden von Fusion. dll, dass die CLR geladen wird.</span><span class="sxs-lookup"><span data-stu-id="5944a-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="5944a-128">Dies liegt daran, dass die Funktionen in Fusion. dll nun Wrapper sind, deren Implementierungen von der Laufzeit bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5944a-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5944a-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5944a-129">Requirements</span></span>  
 <span data-ttu-id="5944a-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5944a-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5944a-131">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="5944a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5944a-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5944a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5944a-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5944a-133">See also</span></span>

- [<span data-ttu-id="5944a-134">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="5944a-134">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
