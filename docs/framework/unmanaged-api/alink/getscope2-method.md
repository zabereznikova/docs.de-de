---
title: GetScope2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3c11eeeb4eece495a7ccbe51c7e04d077e497ce
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494570"
---
# <a name="getscope2-method"></a><span data-ttu-id="36b88-102">GetScope2-Methode</span><span class="sxs-lookup"><span data-stu-id="36b88-102">GetScope2 Method</span></span>
<span data-ttu-id="36b88-103">Ruft eine Importgültigkeitsbereich ab.</span><span class="sxs-lookup"><span data-stu-id="36b88-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36b88-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="36b88-104">Syntax</span></span>  
  
```  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="36b88-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="36b88-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="36b88-106">ID der Zielassembly.</span><span class="sxs-lookup"><span data-stu-id="36b88-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="36b88-107">ID der Datei an, zu importieren.</span><span class="sxs-lookup"><span data-stu-id="36b88-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="36b88-108">Nullbasierte Bereich importiert.</span><span class="sxs-lookup"><span data-stu-id="36b88-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="36b88-109">Zeiger auf empfängt [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) Schnittstelle für den angegebenen Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="36b88-109">Receives pointer to [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36b88-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="36b88-110">Return Value</span></span>  
 <span data-ttu-id="36b88-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="36b88-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36b88-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36b88-112">Requirements</span></span>  
 <span data-ttu-id="36b88-113">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="36b88-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36b88-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36b88-114">See also</span></span>
- [<span data-ttu-id="36b88-115">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36b88-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="36b88-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36b88-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="36b88-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="36b88-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
