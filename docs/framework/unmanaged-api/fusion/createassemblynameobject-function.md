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
ms.openlocfilehash: 995f1064c2f40005c4a19ef034d7edfd668b5d51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704161"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="7eb12-102">CreateAssemblyNameObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="7eb12-102">CreateAssemblyNameObject Function</span></span>

<span data-ttu-id="7eb12-103">Ruft einen Schnittstellen Zeiger auf eine [IAssemblyName](iassemblyname-interface.md) -Instanz ab, die die eindeutige Identität der Assembly mit dem angegebenen Namen darstellt.</span><span class="sxs-lookup"><span data-stu-id="7eb12-103">Gets an interface pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eb12-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7eb12-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="7eb12-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7eb12-105">Parameters</span></span>  

 `ppAssemblyNameObj`  
 <span data-ttu-id="7eb12-106">vorgenommen Der zurückgegebene `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="7eb12-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="7eb12-107">in Der Name der Assembly, für die die neue Instanz erstellt werden soll `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="7eb12-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7eb12-108">in Flags, die an den Objektkonstruktor übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7eb12-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="7eb12-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="7eb12-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7eb12-110">`pvReserved` muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="7eb12-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eb12-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7eb12-111">Requirements</span></span>  

 <span data-ttu-id="7eb12-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eb12-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eb12-113">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7eb12-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7eb12-114">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7eb12-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7eb12-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eb12-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb12-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7eb12-116">See also</span></span>

- [<span data-ttu-id="7eb12-117">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7eb12-117">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="7eb12-118">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="7eb12-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
