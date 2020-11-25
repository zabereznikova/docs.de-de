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
ms.openlocfilehash: 828c7660d6c006e700302d119ce4caf7d76e5d84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728562"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="2b93f-102">IsFrameworkAssembly-Funktion</span><span class="sxs-lookup"><span data-stu-id="2b93f-102">IsFrameworkAssembly Function</span></span>

<span data-ttu-id="2b93f-103">Ruft einen Wert ab, der angibt, ob die angegebene Assembly verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="2b93f-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b93f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b93f-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b93f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b93f-105">Parameters</span></span>  

 `pwzAssemblyReference`  
 <span data-ttu-id="2b93f-106">in Der Name der zu Überprüfung enden Assembly.</span><span class="sxs-lookup"><span data-stu-id="2b93f-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="2b93f-107">vorgenommen Ein boolescher Wert, der angibt, ob die Assembly verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="2b93f-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="2b93f-108">in Eine nicht kanonische Zeichenfolge, die die eindeutige Identität der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="2b93f-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="2b93f-109">[in] Die Größe des `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="2b93f-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b93f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b93f-110">Remarks</span></span>  

 <span data-ttu-id="2b93f-111">Der- `pwzAssemblyReference` Parameter ist ein Zeiger auf eine Zeichenfolge, die den Namen einer Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="2b93f-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="2b93f-112">Wenn diese Assembly Teil des .NET Framework ist, enthält der- `pbIsFrameworkAssembly` Parameter den booleschen Wert `true` .</span><span class="sxs-lookup"><span data-stu-id="2b93f-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="2b93f-113">Wenn die benannte Assembly nicht Teil der .NET Framework ist, oder wenn der- `pwzAssemblyReference` Parameter keine Assembly benannt hat, `pbIsFrameworkAssembly` enthält einen booleschen Wert von `false` .</span><span class="sxs-lookup"><span data-stu-id="2b93f-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b93f-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2b93f-114">Requirements</span></span>  

 <span data-ttu-id="2b93f-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b93f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b93f-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b93f-116">See also</span></span>

- [<span data-ttu-id="2b93f-117">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="2b93f-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
