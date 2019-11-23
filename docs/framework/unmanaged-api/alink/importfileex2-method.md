---
title: ImportFileEx2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
ms.openlocfilehash: 7e270dbfc63c03e77cb4b0694296e48c2035b8a6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445692"
---
# <a name="importfileex2-method"></a><span data-ttu-id="57de4-102">ImportFileEx2-Methode</span><span class="sxs-lookup"><span data-stu-id="57de4-102">ImportFileEx2 Method</span></span>
<span data-ttu-id="57de4-103">Imports assemblies and unbound modules.</span><span class="sxs-lookup"><span data-stu-id="57de4-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="57de4-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span><span class="sxs-lookup"><span data-stu-id="57de4-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57de4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="57de4-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="57de4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="57de4-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="57de4-107">Name of file to be imported.</span><span class="sxs-lookup"><span data-stu-id="57de4-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="57de4-108">Optional name of target file.</span><span class="sxs-lookup"><span data-stu-id="57de4-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="57de4-109">Optional import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="57de4-109">Optional import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="57de4-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span><span class="sxs-lookup"><span data-stu-id="57de4-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="57de4-111">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="57de4-111">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="57de4-112">Receives unique ID for the assembly or file.</span><span class="sxs-lookup"><span data-stu-id="57de4-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="57de4-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="57de4-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="57de4-114">Can be NULL if the file is not an assembly.</span><span class="sxs-lookup"><span data-stu-id="57de4-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="57de4-115">Receives the number of files and/or scopes imported.</span><span class="sxs-lookup"><span data-stu-id="57de4-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57de4-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="57de4-116">Return Value</span></span>  
 <span data-ttu-id="57de4-117">Returns S_OK if the method succeeds.</span><span class="sxs-lookup"><span data-stu-id="57de4-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57de4-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="57de4-118">Requirements</span></span>  
 <span data-ttu-id="57de4-119">Requires alink.h.</span><span class="sxs-lookup"><span data-stu-id="57de4-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57de4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57de4-120">See also</span></span>

- [<span data-ttu-id="57de4-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57de4-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="57de4-122">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57de4-122">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="57de4-123">Alink-API</span><span class="sxs-lookup"><span data-stu-id="57de4-123">ALink API</span></span>](index.md)
