---
title: SetAssemblyProps-Methode
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
ms.openlocfilehash: 4bfad8b985a8ef059031464e99a8004842b276c0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445572"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="7b94c-102">SetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="7b94c-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="7b94c-103">Assigns assembly-level properties.</span><span class="sxs-lookup"><span data-stu-id="7b94c-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b94c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b94c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b94c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7b94c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7b94c-106">ID of the assembly.</span><span class="sxs-lookup"><span data-stu-id="7b94c-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="7b94c-107">File that defines the property.</span><span class="sxs-lookup"><span data-stu-id="7b94c-107">File that defines the property.</span></span> <span data-ttu-id="7b94c-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span><span class="sxs-lookup"><span data-stu-id="7b94c-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="7b94c-109">Indicates the option to modify.</span><span class="sxs-lookup"><span data-stu-id="7b94c-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="7b94c-110">New value of the option.</span><span class="sxs-lookup"><span data-stu-id="7b94c-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b94c-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7b94c-111">Return Value</span></span>  
 <span data-ttu-id="7b94c-112">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="7b94c-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b94c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b94c-113">Requirements</span></span>  
 <span data-ttu-id="7b94c-114">Requires alink.h.</span><span class="sxs-lookup"><span data-stu-id="7b94c-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b94c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b94c-115">See also</span></span>

- [<span data-ttu-id="7b94c-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b94c-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7b94c-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b94c-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7b94c-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="7b94c-118">ALink API</span></span>](index.md)
