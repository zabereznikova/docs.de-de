---
title: ExportNestedTypeForwarder-Methode
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
ms.openlocfilehash: cc81ccd1c754e3d34c54737f4560b4f81d5cc916
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438413"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="edf0e-102">ExportNestedTypeForwarder-Methode</span><span class="sxs-lookup"><span data-stu-id="edf0e-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="edf0e-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span><span class="sxs-lookup"><span data-stu-id="edf0e-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edf0e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="edf0e-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="edf0e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="edf0e-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="edf0e-106">ID of the assembly to export from.</span><span class="sxs-lookup"><span data-stu-id="edf0e-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="edf0e-107">File token or assembly ID of file that defines the type.</span><span class="sxs-lookup"><span data-stu-id="edf0e-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="edf0e-108">Token for the type.</span><span class="sxs-lookup"><span data-stu-id="edf0e-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="edf0e-109">Token of parent type.</span><span class="sxs-lookup"><span data-stu-id="edf0e-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="edf0e-110">Fully qualified type name to export.</span><span class="sxs-lookup"><span data-stu-id="edf0e-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="edf0e-111">`ComType` flags such as `tdPublic` or `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="edf0e-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="edf0e-112">Receives token of export type.</span><span class="sxs-lookup"><span data-stu-id="edf0e-112">Receives token of export type.</span></span> <span data-ttu-id="edf0e-113">This is necessary only for emitting nested types.</span><span class="sxs-lookup"><span data-stu-id="edf0e-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="edf0e-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="edf0e-114">Return Value</span></span>  
 <span data-ttu-id="edf0e-115">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="edf0e-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edf0e-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="edf0e-116">Requirements</span></span>  
 <span data-ttu-id="edf0e-117">Requires alink.h</span><span class="sxs-lookup"><span data-stu-id="edf0e-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edf0e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edf0e-118">See also</span></span>

- [<span data-ttu-id="edf0e-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="edf0e-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="edf0e-120">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="edf0e-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="edf0e-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="edf0e-121">ALink API</span></span>](index.md)
