---
title: GetScope Methode1
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
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4cb51efc3f431dac4a10cc7582e2b43500ccba15
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getscope-method1"></a><span data-ttu-id="acce7-102">GetScope Methode1</span><span class="sxs-lookup"><span data-stu-id="acce7-102">GetScope Method1</span></span>
<span data-ttu-id="acce7-103">Ruft eine Importgültigkeitsbereich ab.</span><span class="sxs-lookup"><span data-stu-id="acce7-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acce7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="acce7-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="acce7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="acce7-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="acce7-106">Eindeutige ID der Assembly zu importieren.</span><span class="sxs-lookup"><span data-stu-id="acce7-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="acce7-107">Eindeutige ID der Datei zum Importieren aus.</span><span class="sxs-lookup"><span data-stu-id="acce7-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="acce7-108">Nullbasierter Gültigkeitsbereich zu importieren.</span><span class="sxs-lookup"><span data-stu-id="acce7-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="acce7-109">Empfängt [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Schnittstelle für den Bereich.</span><span class="sxs-lookup"><span data-stu-id="acce7-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acce7-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="acce7-110">Return Value</span></span>  
 <span data-ttu-id="acce7-111">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="acce7-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acce7-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="acce7-112">Requirements</span></span>  
 <span data-ttu-id="acce7-113">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="acce7-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acce7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acce7-114">See Also</span></span>  
 [<span data-ttu-id="acce7-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="acce7-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="acce7-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="acce7-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="acce7-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="acce7-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
