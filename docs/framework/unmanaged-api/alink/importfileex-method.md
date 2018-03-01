---
title: ImportFileEx-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dc2af9db27c5194a1bdcef875b8db8d458d0edfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="importfileex-method"></a><span data-ttu-id="4cc32-102">ImportFileEx-Methode</span><span class="sxs-lookup"><span data-stu-id="4cc32-102">ImportFileEx Method</span></span>
<span data-ttu-id="4cc32-103">Importe angegebene Assembly oder ein ungebundener Modul.</span><span class="sxs-lookup"><span data-stu-id="4cc32-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cc32-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4cc32-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="4cc32-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4cc32-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="4cc32-106">Vollständig qualifizierte Name der Datei, aus denen importiert.</span><span class="sxs-lookup"><span data-stu-id="4cc32-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="4cc32-107">Optionale Name der Zieldatei.</span><span class="sxs-lookup"><span data-stu-id="4cc32-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="4cc32-108">Bei "true", ImportTypes verwendet wird, andernfalls importieren muss manuell durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4cc32-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="4cc32-109">Flags an, zu übergebende [OpenScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="4cc32-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="4cc32-110">Empfängt die ID der zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="4cc32-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="4cc32-111">Empfängt Import assemblygültigkeitsbereich [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4cc32-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="4cc32-112">Wird auf NULL festgelegt werden, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="4cc32-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="4cc32-113">Empfängt die Anzahl der importierten Dateien und/oder Bereiche.</span><span class="sxs-lookup"><span data-stu-id="4cc32-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cc32-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4cc32-114">Return Value</span></span>  
 <span data-ttu-id="4cc32-115">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4cc32-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cc32-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4cc32-116">Requirements</span></span>  
 <span data-ttu-id="4cc32-117">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="4cc32-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc32-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cc32-118">See Also</span></span>  
 [<span data-ttu-id="4cc32-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4cc32-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="4cc32-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4cc32-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="4cc32-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="4cc32-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
