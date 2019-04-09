---
title: IsFrameworkAssembly-Funktion
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6c715183d3ae04130b729a9680335d65959836a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104064"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="0bb1d-102">IsFrameworkAssembly-Funktion</span><span class="sxs-lookup"><span data-stu-id="0bb1d-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="0bb1d-103">Ruft einen Wert, der angibt, ob die angegebene Assembly verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bb1d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bb1d-104">Syntax</span></span>  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bb1d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0bb1d-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="0bb1d-106">[in] Der Name des zu überprüfenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="0bb1d-107">[out] Ein boolescher Wert, der angibt, ob die Assembly verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="0bb1d-108">[in] Eine uncanonicalized-Zeichenfolge, die eindeutige Identität der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="0bb1d-109">[in] Die Größe des `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bb1d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0bb1d-110">Remarks</span></span>  
 <span data-ttu-id="0bb1d-111">Die `pwzAssemblyReference` Parameter ist ein Zeiger auf eine Zeichenfolge, die den Namen einer Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="0bb1d-112">Wenn diese Assembly Bestandteil von .NET Framework ist die `pbIsFrameworkAssembly` Parameter enthält einen booleschen Wert der `true`.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="0bb1d-113">Wenn die benannte Assembly nicht als Teil von .NET Framework ist oder wenn die `pwzAssemblyReference` Parameter gibt nicht an eine Assembly `pbIsFrameworkAssembly` enthält einen booleschen Wert der `false`.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bb1d-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0bb1d-114">Requirements</span></span>  
 <span data-ttu-id="0bb1d-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bb1d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bb1d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bb1d-116">See also</span></span>

- [<span data-ttu-id="0bb1d-117">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="0bb1d-117">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
