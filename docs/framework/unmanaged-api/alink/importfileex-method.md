---
title: ImportFileEx-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.ImportFileEx
api_location: alink.dll
api_type: COM
f1_keywords: ImportFileEx
helpviewer_keywords: ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 71a7bc1ba9f23f1c581ca3528752e04003d9857c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="importfileex-method"></a><span data-ttu-id="b32cb-102">ImportFileEx-Methode</span><span class="sxs-lookup"><span data-stu-id="b32cb-102">ImportFileEx Method</span></span>
<span data-ttu-id="b32cb-103">Importe angegebene Assembly oder ein ungebundener Modul.</span><span class="sxs-lookup"><span data-stu-id="b32cb-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b32cb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b32cb-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="b32cb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b32cb-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="b32cb-106">Vollständig qualifizierte Name der Datei, aus denen importiert.</span><span class="sxs-lookup"><span data-stu-id="b32cb-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="b32cb-107">Optionale Name der Zieldatei.</span><span class="sxs-lookup"><span data-stu-id="b32cb-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="b32cb-108">Bei "true", ImportTypes verwendet wird, andernfalls importieren muss manuell durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b32cb-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="b32cb-109">Flags an, zu übergebende [OpenScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="b32cb-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="b32cb-110">Empfängt die ID der zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="b32cb-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="b32cb-111">Empfängt Import assemblygültigkeitsbereich [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b32cb-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="b32cb-112">Wird auf NULL festgelegt werden, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="b32cb-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="b32cb-113">Empfängt die Anzahl der importierten Dateien und/oder Bereiche.</span><span class="sxs-lookup"><span data-stu-id="b32cb-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b32cb-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b32cb-114">Return Value</span></span>  
 <span data-ttu-id="b32cb-115">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b32cb-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b32cb-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b32cb-116">Requirements</span></span>  
 <span data-ttu-id="b32cb-117">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="b32cb-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b32cb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b32cb-118">See Also</span></span>  
 [<span data-ttu-id="b32cb-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b32cb-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b32cb-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b32cb-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b32cb-121">ALink-API</span><span class="sxs-lookup"><span data-stu-id="b32cb-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
