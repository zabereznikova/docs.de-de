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
ms.openlocfilehash: d76e9b4e18b46d0b546d6c66fa572c35cb9fcefe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741772"
---
# <a name="importfile-method"></a><span data-ttu-id="ce4c1-102">ImportFile-Methode</span><span class="sxs-lookup"><span data-stu-id="ce4c1-102">ImportFile Method</span></span>
<span data-ttu-id="ce4c1-103">Assemblys und ungebundenen Modulen importiert.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce4c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce4c1-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce4c1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ce4c1-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="ce4c1-106">Voll gekennzeichnete Name des zu importierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="ce4c1-107">Optionale Ausgabedateinamen, die verwendet werden kann, um die Datei umzubenennen, da sie in der Assembly verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="ce4c1-108">True gibt an, ImportTypes wird verwendet, andernfalls importieren muss manuell durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="ce4c1-109">Zeiger auf das token, wo eine eindeutige Datei-ID gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="ce4c1-110">Die Datei kann es sich um eine Assembly oder eine Datei sein.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="ce4c1-111">Zeiger auf empfängt [IMetaDataAssemblyImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ce4c1-111">Receives pointer to [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="ce4c1-112">NULL kann sein, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="ce4c1-113">Zeiger auf die Anzahl der Dateien bzw. Bereiche, die importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce4c1-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ce4c1-114">Return Value</span></span>  
 <span data-ttu-id="ce4c1-115">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="ce4c1-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce4c1-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce4c1-116">Requirements</span></span>  
 <span data-ttu-id="ce4c1-117">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="ce4c1-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce4c1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce4c1-118">See also</span></span>

- [<span data-ttu-id="ce4c1-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce4c1-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ce4c1-120">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce4c1-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ce4c1-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="ce4c1-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
