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
ms.openlocfilehash: 6956fd0bd8217a3b0b44f48cabc80d0c95db8f36
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494363"
---
# <a name="importfileex-method"></a><span data-ttu-id="ad628-102">ImportFileEx-Methode</span><span class="sxs-lookup"><span data-stu-id="ad628-102">ImportFileEx Method</span></span>
<span data-ttu-id="ad628-103">Importiert die angegebene Assembly oder ein ungebundenes Modul angegebene.</span><span class="sxs-lookup"><span data-stu-id="ad628-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad628-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad628-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ad628-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ad628-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="ad628-106">Voll gekennzeichnete Name der Datei, aus denen importiert.</span><span class="sxs-lookup"><span data-stu-id="ad628-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="ad628-107">Optionaler Name der Zieldatei.</span><span class="sxs-lookup"><span data-stu-id="ad628-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="ad628-108">True gibt an, ImportTypes wird verwendet, andernfalls importieren muss manuell durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ad628-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="ad628-109">Flags, die zu übergebende [OpenScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="ad628-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="ad628-110">Empfängt die ID der Datei importiert wird.</span><span class="sxs-lookup"><span data-stu-id="ad628-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="ad628-111">Import Assemblybereich empfängt [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ad628-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="ad628-112">Wird auf NULL festgelegt werden, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="ad628-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="ad628-113">Empfängt die Anzahl der importierten Dateien bzw. Bereiche.</span><span class="sxs-lookup"><span data-stu-id="ad628-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad628-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ad628-114">Return Value</span></span>  
 <span data-ttu-id="ad628-115">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="ad628-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad628-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ad628-116">Requirements</span></span>  
 <span data-ttu-id="ad628-117">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="ad628-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad628-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad628-118">See also</span></span>
- [<span data-ttu-id="ad628-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad628-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ad628-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad628-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ad628-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="ad628-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
