---
title: ImportTypes-Methode
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6591fb4a2b4944dc0d02f70f0f90ffd87e071c47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735000"
---
# <a name="importtypes-method"></a><span data-ttu-id="a47f8-102">ImportTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="a47f8-102">ImportTypes Method</span></span>
<span data-ttu-id="a47f8-103">Initiiert das Importieren von Typen aus jedem Bereich über importiert [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="a47f8-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a47f8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a47f8-104">Syntax</span></span>  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a47f8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a47f8-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a47f8-106">Die ID der Assembly zu importieren.</span><span class="sxs-lookup"><span data-stu-id="a47f8-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a47f8-107">Die ID der Datei zum Importieren aus.</span><span class="sxs-lookup"><span data-stu-id="a47f8-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="a47f8-108">Nullbasierte Bereich importiert.</span><span class="sxs-lookup"><span data-stu-id="a47f8-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="a47f8-109">Enumeratorhandle für die Typen empfängt in diesem Bereich.</span><span class="sxs-lookup"><span data-stu-id="a47f8-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="a47f8-110">Empfängt optional [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a47f8-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="a47f8-111">Empfängt optional die Anzahl der Typen im angegebenen Bereich.</span><span class="sxs-lookup"><span data-stu-id="a47f8-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a47f8-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a47f8-112">Return Value</span></span>  
 <span data-ttu-id="a47f8-113">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="a47f8-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a47f8-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a47f8-114">Requirements</span></span>  
 <span data-ttu-id="a47f8-115">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="a47f8-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a47f8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a47f8-116">See also</span></span>
- [<span data-ttu-id="a47f8-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47f8-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a47f8-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a47f8-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a47f8-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="a47f8-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
