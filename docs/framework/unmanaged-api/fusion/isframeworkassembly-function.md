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
ms.openlocfilehash: 269e3702c21532f377735ba6087abb1603dde4f7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796315"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="9dd60-102">IsFrameworkAssembly-Funktion</span><span class="sxs-lookup"><span data-stu-id="9dd60-102">IsFrameworkAssembly Function</span></span>
<span data-ttu-id="9dd60-103">Ruft einen Wert ab, der angibt, ob die angegebene Assembly verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="9dd60-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dd60-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9dd60-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dd60-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9dd60-105">Parameters</span></span>  
 `pwzAssemblyReference`  
 <span data-ttu-id="9dd60-106">in Der Name der zu Überprüfung enden Assembly.</span><span class="sxs-lookup"><span data-stu-id="9dd60-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="9dd60-107">vorgenommen Ein boolescher Wert, der angibt, ob die Assembly verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="9dd60-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="9dd60-108">in Eine nicht kanonische Zeichenfolge, die die eindeutige Identität der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="9dd60-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="9dd60-109">[in] Die Größe des `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="9dd60-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9dd60-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9dd60-110">Remarks</span></span>  
 <span data-ttu-id="9dd60-111">Der `pwzAssemblyReference` -Parameter ist ein Zeiger auf eine Zeichenfolge, die den Namen einer Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="9dd60-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="9dd60-112">Wenn diese Assembly Teil des .NET Framework ist, enthält der `pbIsFrameworkAssembly` -Parameter den booleschen `true`Wert.</span><span class="sxs-lookup"><span data-stu-id="9dd60-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="9dd60-113">Wenn die benannte Assembly nicht Teil der .NET Framework ist, oder wenn der `pwzAssemblyReference` -Parameter keine Assembly benannt hat, `pbIsFrameworkAssembly` enthält einen booleschen Wert von `false`.</span><span class="sxs-lookup"><span data-stu-id="9dd60-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dd60-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9dd60-114">Requirements</span></span>  
 <span data-ttu-id="9dd60-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dd60-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dd60-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dd60-116">See also</span></span>

- [<span data-ttu-id="9dd60-117">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="9dd60-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
