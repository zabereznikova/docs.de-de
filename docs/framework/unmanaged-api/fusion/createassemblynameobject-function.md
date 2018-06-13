---
title: CreateAssemblyNameObject-Funktion
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5433c49db8e507c6026ab0e87040dd5634ad0808
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430437"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="a43d6-102">CreateAssemblyNameObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="a43d6-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="a43d6-103">Ruft einen Schnittstellenzeiger auf eine [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) Instanz, die die eindeutige Identität der Assembly mit dem angegebenen Namen darstellt.</span><span class="sxs-lookup"><span data-stu-id="a43d6-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a43d6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a43d6-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a43d6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a43d6-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="a43d6-106">[out] Das zurückgegebene `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="a43d6-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="a43d6-107">[in] Der Name der Assembly, für die Erstellung des neuen `IAssemblyName` Instanz.</span><span class="sxs-lookup"><span data-stu-id="a43d6-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a43d6-108">[in] Flags, die an den Objektkonstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="a43d6-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="a43d6-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="a43d6-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="a43d6-110">`pvReserved` ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="a43d6-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a43d6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a43d6-111">Requirements</span></span>  
 <span data-ttu-id="a43d6-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a43d6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a43d6-113">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="a43d6-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a43d6-114">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a43d6-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a43d6-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a43d6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a43d6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a43d6-116">See Also</span></span>  
 [<span data-ttu-id="a43d6-117">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a43d6-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="a43d6-118">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="a43d6-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
