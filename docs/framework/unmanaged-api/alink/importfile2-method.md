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
ms.openlocfilehash: 1193af7b7375dfd3367c12fdb0067c9c30c614f0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741754"
---
# <a name="importfile2-method"></a><span data-ttu-id="2ed85-102">ImportFile2-Methode</span><span class="sxs-lookup"><span data-stu-id="2ed85-102">ImportFile2 Method</span></span>
<span data-ttu-id="2ed85-103">Assemblys und ungebundenen Modulen importiert.</span><span class="sxs-lookup"><span data-stu-id="2ed85-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="2ed85-104">Diese Methode entspricht [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), aber Sie funktioniert auch, wenn die zu importierende Datei auf dem Datenträger nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2ed85-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ed85-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ed85-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="2ed85-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ed85-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="2ed85-107">Name des zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="2ed85-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="2ed85-108">Optionale Ausgabedateinamen, die verwendet werden kann, um die Datei umzubenennen, da sie in der Assembly verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="2ed85-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="2ed85-109">Optionaler anzugebender Bereich [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2ed85-109">Optional scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="2ed85-110">True gibt an, ImportTypes wird verwendet, andernfalls importieren muss manuell durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2ed85-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="2ed85-111">Empfängt die ID für die Datei oder Assembly.</span><span class="sxs-lookup"><span data-stu-id="2ed85-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="2ed85-112">Empfängt die [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2ed85-112">Receives the [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="2ed85-113">NULL, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="2ed85-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="2ed85-114">Empfängt die Anzahl Dateien bzw. Bereiche nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="2ed85-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ed85-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2ed85-115">Return Value</span></span>  
 <span data-ttu-id="2ed85-116">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2ed85-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ed85-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ed85-117">Requirements</span></span>  
 <span data-ttu-id="2ed85-118">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="2ed85-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed85-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ed85-119">See also</span></span>

- [<span data-ttu-id="2ed85-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ed85-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="2ed85-121">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ed85-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="2ed85-122">Alink-API</span><span class="sxs-lookup"><span data-stu-id="2ed85-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
