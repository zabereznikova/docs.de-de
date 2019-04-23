---
title: ImportFile-Methode
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69e48c6c3179ced167fdc39ae4df859f161727ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077250"
---
# <a name="importfile-method"></a><span data-ttu-id="08565-102">ImportFile-Methode</span><span class="sxs-lookup"><span data-stu-id="08565-102">ImportFile Method</span></span>
<span data-ttu-id="08565-103">Assemblys und ungebundenen Modulen importiert.</span><span class="sxs-lookup"><span data-stu-id="08565-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08565-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08565-104">Syntax</span></span>  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="08565-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08565-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="08565-106">Voll gekennzeichnete Name des zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="08565-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="08565-107">Optionale Ausgabedateinamen, die verwendet werden kann, um die Datei umzubenennen, da sie in der Assembly verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="08565-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="08565-108">True gibt an, ImportTypes wird verwendet, andernfalls importieren muss manuell durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="08565-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="08565-109">Zeiger auf das token, wo eine eindeutige Datei-ID gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="08565-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="08565-110">Die Datei kann es sich um eine Assembly oder eine Datei sein.</span><span class="sxs-lookup"><span data-stu-id="08565-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="08565-111">Zeiger auf empfängt [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="08565-111">Receives pointer to [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="08565-112">NULL kann sein, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="08565-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="08565-113">Zeiger auf die Anzahl der Dateien bzw. Bereiche, die importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="08565-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08565-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="08565-114">Return Value</span></span>  
 <span data-ttu-id="08565-115">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="08565-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08565-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08565-116">Requirements</span></span>  
 <span data-ttu-id="08565-117">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="08565-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08565-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08565-118">See also</span></span>

- [<span data-ttu-id="08565-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08565-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="08565-120">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08565-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="08565-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="08565-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
