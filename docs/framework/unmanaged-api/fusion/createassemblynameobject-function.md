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
ms.openlocfilehash: 1412231b53763ce8e6c2400497396d2f178d8e7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666292"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="63435-102">CreateAssemblyNameObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="63435-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="63435-103">Ruft einen Schnittstellenzeiger auf ein [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) -Instanz, die eindeutige Identität der Assembly mit dem angegebenen Namen darstellt.</span><span class="sxs-lookup"><span data-stu-id="63435-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63435-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63435-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63435-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="63435-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="63435-106">[out] Das zurückgegebene `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="63435-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="63435-107">[in] Der Name der Assembly, für die zum Erstellen des neuen `IAssemblyName` Instanz.</span><span class="sxs-lookup"><span data-stu-id="63435-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="63435-108">[in] Flags, die an den Objektkonstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="63435-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="63435-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="63435-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="63435-110">`pvReserved` ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="63435-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63435-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63435-111">Requirements</span></span>  
 <span data-ttu-id="63435-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63435-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63435-113">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="63435-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="63435-114">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="63435-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="63435-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63435-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63435-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63435-116">See also</span></span>
- [<span data-ttu-id="63435-117">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63435-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="63435-118">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="63435-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
