---
title: ImportFileEx-Methode
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
ms.openlocfilehash: bee7db61beb9ed8c00cf584924be690a67d92eac
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446954"
---
# <a name="importfileex-method"></a><span data-ttu-id="603b4-102">ImportFileEx-Methode</span><span class="sxs-lookup"><span data-stu-id="603b4-102">ImportFileEx Method</span></span>
<span data-ttu-id="603b4-103">Imports indicated assembly or unbound module.</span><span class="sxs-lookup"><span data-stu-id="603b4-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="603b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="603b4-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="603b4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="603b4-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="603b4-106">Fully qualified name of file from which to import.</span><span class="sxs-lookup"><span data-stu-id="603b4-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="603b4-107">Optional name of target file.</span><span class="sxs-lookup"><span data-stu-id="603b4-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="603b4-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span><span class="sxs-lookup"><span data-stu-id="603b4-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="603b4-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="603b4-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="603b4-110">Receives ID of the file being imported.</span><span class="sxs-lookup"><span data-stu-id="603b4-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="603b4-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="603b4-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="603b4-112">Is set to NULL if file is not an assembly.</span><span class="sxs-lookup"><span data-stu-id="603b4-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="603b4-113">Receives count of imported files and/or scopes.</span><span class="sxs-lookup"><span data-stu-id="603b4-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="603b4-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="603b4-114">Return Value</span></span>  
 <span data-ttu-id="603b4-115">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="603b4-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="603b4-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="603b4-116">Requirements</span></span>  
 <span data-ttu-id="603b4-117">Requires alink.h.</span><span class="sxs-lookup"><span data-stu-id="603b4-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="603b4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="603b4-118">See also</span></span>

- [<span data-ttu-id="603b4-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="603b4-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="603b4-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="603b4-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="603b4-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="603b4-121">ALink API</span></span>](index.md)
