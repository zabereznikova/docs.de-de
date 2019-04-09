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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 784e58e0c5c2329705671580d53763f2ac30f0b2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201350"
---
# <a name="importfileex2-method"></a><span data-ttu-id="d0edc-102">ImportFileEx2-Methode</span><span class="sxs-lookup"><span data-stu-id="d0edc-102">ImportFileEx2 Method</span></span>
<span data-ttu-id="d0edc-103">Assemblys und ungebundenen Modulen importiert.</span><span class="sxs-lookup"><span data-stu-id="d0edc-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="d0edc-104">Diese Methode entspricht [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), aber Sie funktioniert auch, wenn die zu importierende Datei auf dem Datenträger nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d0edc-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0edc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0edc-105">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="d0edc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d0edc-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="d0edc-107">Name des zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="d0edc-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="d0edc-108">Optionaler Name der Zieldatei.</span><span class="sxs-lookup"><span data-stu-id="d0edc-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="d0edc-109">Optionale importierte Bereich [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d0edc-109">Optional import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="d0edc-110">True gibt an, ImportTypes wird verwendet, andernfalls importieren muss manuell durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d0edc-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="d0edc-111">Flags, die zu übergebende [OpenScope-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="d0edc-111">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="d0edc-112">Empfängt die eindeutige ID für die Assembly oder Datei.</span><span class="sxs-lookup"><span data-stu-id="d0edc-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="d0edc-113">Import Assemblybereich empfängt [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d0edc-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="d0edc-114">NULL kann sein, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="d0edc-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="d0edc-115">Empfängt die Anzahl der Dateien bzw. Bereiche nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="d0edc-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0edc-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d0edc-116">Return Value</span></span>  
 <span data-ttu-id="d0edc-117">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="d0edc-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0edc-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0edc-118">Requirements</span></span>  
 <span data-ttu-id="d0edc-119">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="d0edc-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0edc-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0edc-120">See also</span></span>

- [<span data-ttu-id="d0edc-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0edc-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="d0edc-122">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0edc-122">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="d0edc-123">ALink-API</span><span class="sxs-lookup"><span data-stu-id="d0edc-123">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
