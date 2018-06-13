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
ms.openlocfilehash: c3fd130759ab11b54b597d5c099c33dab93070ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429249"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="58a8a-102">IsFrameworkAssembly-Funktion</span><span class="sxs-lookup"><span data-stu-id="58a8a-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="58a8a-103">Ruft einen Wert, der angibt, ob die angegebene Assembly verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="58a8a-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58a8a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="58a8a-104">Syntax</span></span>  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58a8a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="58a8a-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="58a8a-106">[in] Der Name der Assembly zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="58a8a-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="58a8a-107">[out] Ein boolescher Wert, der angibt, ob die Assembly verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="58a8a-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="58a8a-108">[in] Eine uncanonicalized Zeichenfolge, die eindeutige Identität der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="58a8a-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="58a8a-109">[in] Die Größe des `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="58a8a-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58a8a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58a8a-110">Remarks</span></span>  
 <span data-ttu-id="58a8a-111">Die `pwzAssemblyReference` Parameter ist ein Zeiger auf eine Zeichenfolge, die den Namen einer Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="58a8a-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="58a8a-112">Wenn diese Assembly Bestandteil von .NET Framework ist die `pbIsFrameworkAssembly` Parameter enthält einen booleschen Wert des `true`.</span><span class="sxs-lookup"><span data-stu-id="58a8a-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="58a8a-113">Wenn der benannte Assembly kein Bestandteil von .NET Framework ist oder wenn die `pwzAssemblyReference` Parameter wird nicht den Namen einer Assembly `pbIsFrameworkAssembly` enthält einen booleschen Wert des `false`.</span><span class="sxs-lookup"><span data-stu-id="58a8a-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58a8a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58a8a-114">Requirements</span></span>  
 <span data-ttu-id="58a8a-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58a8a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a8a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58a8a-116">See Also</span></span>  
 [<span data-ttu-id="58a8a-117">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="58a8a-117">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
