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
ms.openlocfilehash: 00345f6c95c67f0494aa721c662f56a9e98cdd7f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108713"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="8ebd9-102">CreateAssemblyNameObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="8ebd9-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="8ebd9-103">Ruft einen Schnittstellen Zeiger auf eine [IAssemblyName](iassemblyname-interface.md) -Instanz ab, die die eindeutige Identität der Assembly mit dem angegebenen Namen darstellt.</span><span class="sxs-lookup"><span data-stu-id="8ebd9-103">Gets an interface pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ebd9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ebd9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ebd9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ebd9-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="8ebd9-106">vorgenommen Der zurückgegebene `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="8ebd9-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="8ebd9-107">in Der Name der Assembly, für die die neue `IAssemblyName` Instanz erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8ebd9-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8ebd9-108">in Flags, die an den Objektkonstruktor übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8ebd9-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8ebd9-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="8ebd9-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8ebd9-110">`pvReserved` muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="8ebd9-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ebd9-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8ebd9-111">Requirements</span></span>  
 <span data-ttu-id="8ebd9-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ebd9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ebd9-113">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8ebd9-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8ebd9-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8ebd9-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ebd9-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ebd9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebd9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ebd9-116">See also</span></span>

- [<span data-ttu-id="8ebd9-117">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ebd9-117">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="8ebd9-118">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="8ebd9-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
