---
title: GetScope-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 571612796d4e66be9dd8469d748c2380c839ddfa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165781"
---
# <a name="getscope-method"></a><span data-ttu-id="9713c-102">GetScope-Methode</span><span class="sxs-lookup"><span data-stu-id="9713c-102">GetScope Method</span></span>
<span data-ttu-id="9713c-103">Ruft eine Importgültigkeitsbereich ab.</span><span class="sxs-lookup"><span data-stu-id="9713c-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9713c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9713c-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9713c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9713c-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9713c-106">Eindeutige ID der Assembly zu importieren.</span><span class="sxs-lookup"><span data-stu-id="9713c-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9713c-107">Eindeutige ID der Datei zum Importieren aus.</span><span class="sxs-lookup"><span data-stu-id="9713c-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="9713c-108">Nullbasierte Bereich importiert.</span><span class="sxs-lookup"><span data-stu-id="9713c-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="9713c-109">Empfängt [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Schnittstelle für den Bereich.</span><span class="sxs-lookup"><span data-stu-id="9713c-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9713c-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9713c-110">Return Value</span></span>  
 <span data-ttu-id="9713c-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="9713c-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9713c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9713c-112">Requirements</span></span>  
 <span data-ttu-id="9713c-113">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="9713c-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9713c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9713c-114">See also</span></span>

- [<span data-ttu-id="9713c-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9713c-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="9713c-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9713c-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="9713c-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="9713c-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
