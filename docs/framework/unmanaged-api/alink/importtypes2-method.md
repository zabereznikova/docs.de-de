---
title: ImportTypes2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51c696679626a598be422376e9dc89b5add1773d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400490"
---
# <a name="importtypes2-method"></a><span data-ttu-id="4e9ff-102">ImportTypes2-Methode</span><span class="sxs-lookup"><span data-stu-id="4e9ff-102">ImportTypes2 Method</span></span>
<span data-ttu-id="4e9ff-103">Initiiert den Import von Typen.</span><span class="sxs-lookup"><span data-stu-id="4e9ff-103">Initiates the import of types.</span></span> <span data-ttu-id="4e9ff-104">Rufen Sie diese Methode, um zu beginnen, Importieren von Typen aus jedem Bereich über importiert [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="4e9ff-104">Call this method to begin importing types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e9ff-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e9ff-105">Syntax</span></span>  
  
```  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e9ff-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e9ff-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4e9ff-107">ID der Assembly in die importiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4e9ff-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="4e9ff-108">ID der Datei, aus denen importiert.</span><span class="sxs-lookup"><span data-stu-id="4e9ff-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="4e9ff-109">Nullbasierter Gültigkeitsbereich zum Importieren von.</span><span class="sxs-lookup"><span data-stu-id="4e9ff-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="4e9ff-110">Empfängt Enumeratorhandle für die Typen im angegebenen Bereich.</span><span class="sxs-lookup"><span data-stu-id="4e9ff-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="4e9ff-111">Empfängt optional [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="4e9ff-111">Optionally receives [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="4e9ff-112">Empfängt optional die Anzahl der Typen im angegebenen Bereich.</span><span class="sxs-lookup"><span data-stu-id="4e9ff-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e9ff-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4e9ff-113">Return Value</span></span>  
 <span data-ttu-id="4e9ff-114">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e9ff-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e9ff-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e9ff-115">Requirements</span></span>  
 <span data-ttu-id="4e9ff-116">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="4e9ff-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e9ff-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e9ff-117">See Also</span></span>  
 [<span data-ttu-id="4e9ff-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e9ff-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="4e9ff-119">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e9ff-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="4e9ff-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="4e9ff-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
