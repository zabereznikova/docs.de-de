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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b3cf91ad4e048ddfccb4086f36923f33d754ac0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131039"
---
# <a name="importfileex-method"></a><span data-ttu-id="d4d30-102">ImportFileEx-Methode</span><span class="sxs-lookup"><span data-stu-id="d4d30-102">ImportFileEx Method</span></span>
<span data-ttu-id="d4d30-103">Importiert die angegebene Assembly oder ein ungebundenes Modul angegebene.</span><span class="sxs-lookup"><span data-stu-id="d4d30-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4d30-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4d30-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="d4d30-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4d30-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="d4d30-106">Voll gekennzeichnete Name der Datei, aus denen importiert.</span><span class="sxs-lookup"><span data-stu-id="d4d30-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="d4d30-107">Optionaler Name der Zieldatei.</span><span class="sxs-lookup"><span data-stu-id="d4d30-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="d4d30-108">True gibt an, ImportTypes wird verwendet, andernfalls importieren muss manuell durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d4d30-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="d4d30-109">Flags, die zu übergebende [OpenScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="d4d30-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="d4d30-110">Empfängt die ID der Datei importiert wird.</span><span class="sxs-lookup"><span data-stu-id="d4d30-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="d4d30-111">Import Assemblybereich empfängt [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d4d30-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="d4d30-112">Wird auf NULL festgelegt werden, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="d4d30-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="d4d30-113">Empfängt die Anzahl der importierten Dateien bzw. Bereiche.</span><span class="sxs-lookup"><span data-stu-id="d4d30-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4d30-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d4d30-114">Return Value</span></span>  
 <span data-ttu-id="d4d30-115">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="d4d30-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4d30-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4d30-116">Requirements</span></span>  
 <span data-ttu-id="d4d30-117">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="d4d30-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4d30-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4d30-118">See also</span></span>

- [<span data-ttu-id="d4d30-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4d30-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d4d30-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4d30-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d4d30-121">ALink-API</span><span class="sxs-lookup"><span data-stu-id="d4d30-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
