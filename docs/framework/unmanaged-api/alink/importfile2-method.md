---
title: ImportFile2-Methode
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c6279c790e9b28e5f3bac93d5d0fdd411dd8c0d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127269"
---
# <a name="importfile2-method"></a><span data-ttu-id="55dec-102">ImportFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="55dec-102">ImportFile2 Method</span></span>
<span data-ttu-id="55dec-103">Assemblys und ungebundenen Modulen importiert.</span><span class="sxs-lookup"><span data-stu-id="55dec-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="55dec-104">Diese Methode entspricht [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), aber Sie funktioniert auch, wenn die zu importierende Datei auf dem Datenträger nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="55dec-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55dec-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="55dec-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="55dec-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="55dec-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="55dec-107">Name des zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="55dec-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="55dec-108">Optionale Ausgabedateinamen, die verwendet werden kann, um die Datei umzubenennen, da sie in der Assembly verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="55dec-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="55dec-109">Optionaler anzugebender Bereich [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="55dec-109">Optional scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="55dec-110">True gibt an, ImportTypes wird verwendet, andernfalls importieren muss manuell durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="55dec-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="55dec-111">Empfängt die ID für die Datei oder Assembly.</span><span class="sxs-lookup"><span data-stu-id="55dec-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="55dec-112">Empfängt die [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="55dec-112">Receives the [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="55dec-113">NULL, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="55dec-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="55dec-114">Empfängt die Anzahl Dateien bzw. Bereiche nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="55dec-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55dec-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="55dec-115">Return Value</span></span>  
 <span data-ttu-id="55dec-116">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="55dec-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55dec-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="55dec-117">Requirements</span></span>  
 <span data-ttu-id="55dec-118">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="55dec-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55dec-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55dec-119">See also</span></span>

- [<span data-ttu-id="55dec-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55dec-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="55dec-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="55dec-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="55dec-122">Alink-API</span><span class="sxs-lookup"><span data-stu-id="55dec-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
