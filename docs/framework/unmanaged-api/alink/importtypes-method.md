---
title: ImportTypes-Methode
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 39e7cfb3c811a89ae88d6984946f72a9b1f469db
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="importtypes-method"></a><span data-ttu-id="9606b-102">ImportTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="9606b-102">ImportTypes Method</span></span>
<span data-ttu-id="9606b-103">Initiiert das Importieren von Typen aus jedem Bereich über importiert [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="9606b-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9606b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9606b-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="9606b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9606b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9606b-106">Die ID der Assembly zu importieren.</span><span class="sxs-lookup"><span data-stu-id="9606b-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9606b-107">ID der Datei zum Importieren aus.</span><span class="sxs-lookup"><span data-stu-id="9606b-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="9606b-108">Nullbasierter Gültigkeitsbereich zu importieren.</span><span class="sxs-lookup"><span data-stu-id="9606b-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="9606b-109">Enumeratorhandle für die Typen empfängt in diesem Bereich.</span><span class="sxs-lookup"><span data-stu-id="9606b-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="9606b-110">Empfängt optional [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9606b-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="9606b-111">Empfängt optional die Anzahl der Typen im angegebenen Bereich.</span><span class="sxs-lookup"><span data-stu-id="9606b-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9606b-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9606b-112">Return Value</span></span>  
 <span data-ttu-id="9606b-113">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9606b-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9606b-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9606b-114">Requirements</span></span>  
 <span data-ttu-id="9606b-115">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="9606b-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9606b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9606b-116">See Also</span></span>  
 [<span data-ttu-id="9606b-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9606b-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="9606b-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9606b-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="9606b-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="9606b-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
