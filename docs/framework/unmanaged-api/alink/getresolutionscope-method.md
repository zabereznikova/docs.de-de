---
title: GetResolutionScope-Methode
ms.date: 03/30/2017
api_name:
- IALink.GetResolutionScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetResolutionScope
helpviewer_keywords:
- GetResolutionScope method
ms.assetid: 5b48ca60-dacd-44b2-9979-4a5122f00812
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6c2e741df594e265fdef51a602a9a4927733b7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741863"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="12add-102">GetResolutionScope-Methode</span><span class="sxs-lookup"><span data-stu-id="12add-102">GetResolutionScope Method</span></span>
<span data-ttu-id="12add-103">Ruft den Bereich des angegebenen Typs ab.</span><span class="sxs-lookup"><span data-stu-id="12add-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12add-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12add-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="12add-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="12add-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="12add-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="12add-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="12add-107">Datei, die ein Verweis erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="12add-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="12add-108">Token der Datei dieses Typs ist definiert in "," in der Regel mit abgerufen [ImportFile-Methode](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="12add-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="12add-109">Erhält die Assembly oder den Modulverweis.</span><span class="sxs-lookup"><span data-stu-id="12add-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12add-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="12add-110">Return Value</span></span>  
 <span data-ttu-id="12add-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="12add-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12add-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="12add-112">Requirements</span></span>  
 <span data-ttu-id="12add-113">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="12add-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12add-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12add-114">See also</span></span>

- [<span data-ttu-id="12add-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12add-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="12add-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12add-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="12add-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="12add-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
