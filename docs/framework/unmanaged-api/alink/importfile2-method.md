---
title: ImportFile2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ImportFile2
api_location: alink.dll
api_type: COM
f1_keywords: ImportFile2
helpviewer_keywords: ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4d7e842152e84992124ec29cd551c3b5d50a6d61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="importfile2-method"></a><span data-ttu-id="d32c2-102">ImportFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="d32c2-102">ImportFile2 Method</span></span>
<span data-ttu-id="d32c2-103">Imports-Assemblys und ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="d32c2-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="d32c2-104">Diese Methode entspricht [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), aber funktioniert auch, wenn die zu importierende Datei auf dem Datenträger nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d32c2-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d32c2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d32c2-105">Syntax</span></span>  
  
```  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d32c2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d32c2-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="d32c2-107">Name der zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="d32c2-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="d32c2-108">Optionale Ausgabedateiname, der verwendet werden kann, um die Datei zu benennen, wie sie in der Assembly verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="d32c2-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="d32c2-109">Optionaler anzugebender Bereich [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d32c2-109">Optional scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="d32c2-110">Bei "true", ImportTypes verwendet wird, andernfalls importieren muss manuell durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d32c2-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="d32c2-111">Empfängt die ID für die Datei oder Assembly.</span><span class="sxs-lookup"><span data-stu-id="d32c2-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="d32c2-112">Empfängt die [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d32c2-112">Receives the [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="d32c2-113">NULL, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="d32c2-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="d32c2-114">Empfängt die Dateien und/oder Bereiche nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="d32c2-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d32c2-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d32c2-115">Return Value</span></span>  
 <span data-ttu-id="d32c2-116">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d32c2-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d32c2-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d32c2-117">Requirements</span></span>  
 <span data-ttu-id="d32c2-118">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="d32c2-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d32c2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d32c2-119">See Also</span></span>  
 [<span data-ttu-id="d32c2-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d32c2-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="d32c2-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d32c2-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="d32c2-122">ALink-API</span><span class="sxs-lookup"><span data-stu-id="d32c2-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
