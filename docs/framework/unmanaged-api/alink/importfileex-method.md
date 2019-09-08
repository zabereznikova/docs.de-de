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
ms.openlocfilehash: bd138d0418bb9667a86419d719bf0b95a4bb1b12
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777114"
---
# <a name="importfileex-method"></a><span data-ttu-id="aa9a8-102">ImportFileEx-Methode</span><span class="sxs-lookup"><span data-stu-id="aa9a8-102">ImportFileEx Method</span></span>
<span data-ttu-id="aa9a8-103">Importiert die angegebener Assembly oder das nicht gebundene Modul.</span><span class="sxs-lookup"><span data-stu-id="aa9a8-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa9a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa9a8-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="aa9a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa9a8-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="aa9a8-106">Der voll qualifizierte Name der Datei, aus der importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="aa9a8-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="aa9a8-107">Optionaler Name der Zieldatei.</span><span class="sxs-lookup"><span data-stu-id="aa9a8-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="aa9a8-108">TRUE gibt an, dass ImportTypes verwendet wird. andernfalls muss der Import manuell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="aa9a8-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="aa9a8-109">Flags, die an die [OpenScope-Methode](../metadata/imetadatadispenser-openscope-method.md)weitergegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="aa9a8-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="aa9a8-110">Empfängt die ID der Datei, die importiert wird.</span><span class="sxs-lookup"><span data-stu-id="aa9a8-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="aa9a8-111">Empfängt assemblyimportierungsbereich [IMetaDataAssemblyImport Schnittstellen](../metadata/imetadataassemblyimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="aa9a8-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="aa9a8-112">Wird auf NULL festgelegt, wenn die Datei keine Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="aa9a8-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="aa9a8-113">Empfängt die Anzahl importierter Dateien und/oder Bereiche.</span><span class="sxs-lookup"><span data-stu-id="aa9a8-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa9a8-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="aa9a8-114">Return Value</span></span>  
 <span data-ttu-id="aa9a8-115">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="aa9a8-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa9a8-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa9a8-116">Requirements</span></span>  
 <span data-ttu-id="aa9a8-117">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="aa9a8-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa9a8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa9a8-118">See also</span></span>

- [<span data-ttu-id="aa9a8-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa9a8-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="aa9a8-120">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa9a8-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="aa9a8-121">Alink-API</span><span class="sxs-lookup"><span data-stu-id="aa9a8-121">ALink API</span></span>](index.md)
