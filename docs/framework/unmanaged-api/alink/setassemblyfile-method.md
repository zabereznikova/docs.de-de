---
title: SetAssemblyFile-Methode
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 1db4c4ab7e47e223a492e08297ac3cedcb3a27eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445602"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="f822d-102">SetAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="f822d-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="f822d-103">Assigns the name of the assembly to be built.</span><span class="sxs-lookup"><span data-stu-id="f822d-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="f822d-104">Not for use when producing unbound modules.</span><span class="sxs-lookup"><span data-stu-id="f822d-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f822d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f822d-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f822d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f822d-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="f822d-107">Fully qualified name of the manifest file.</span><span class="sxs-lookup"><span data-stu-id="f822d-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="f822d-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="f822d-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="f822d-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f822d-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="f822d-110">Pointer to ID of resulting assembly.</span><span class="sxs-lookup"><span data-stu-id="f822d-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f822d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f822d-111">Return Value</span></span>  
 <span data-ttu-id="f822d-112">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="f822d-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f822d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f822d-113">Requirements</span></span>  
 <span data-ttu-id="f822d-114">Requires alink.h.</span><span class="sxs-lookup"><span data-stu-id="f822d-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f822d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f822d-115">See also</span></span>

- [<span data-ttu-id="f822d-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f822d-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f822d-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f822d-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f822d-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="f822d-118">ALink API</span></span>](index.md)
