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
ms.openlocfilehash: f2b78b35db6306c82e389955c4824875bcf25334
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447224"
---
# <a name="getresolutionscope-method"></a><span data-ttu-id="84cdd-102">GetResolutionScope-Methode</span><span class="sxs-lookup"><span data-stu-id="84cdd-102">GetResolutionScope Method</span></span>
<span data-ttu-id="84cdd-103">Ruft den Bereich eines angegebenen Typs ab.</span><span class="sxs-lookup"><span data-stu-id="84cdd-103">Retrieves the scope of a given type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84cdd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84cdd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResolutionScope(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    mdToken     TargetFile,  
    mdToken*    pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="84cdd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84cdd-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="84cdd-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="84cdd-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="84cdd-107">Die Datei, die einen Verweis benötigt.</span><span class="sxs-lookup"><span data-stu-id="84cdd-107">File that is in need of a reference.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="84cdd-108">Token der Datei, in der der Typ definiert ist, wird normalerweise mit der [ImportFile-Methode](importfile-method.md)abgerufen.</span><span class="sxs-lookup"><span data-stu-id="84cdd-108">Token of file that type is defined in, usually retrieved with [ImportFile Method](importfile-method.md).</span></span>  
  
 `pScope`  
 <span data-ttu-id="84cdd-109">Empfängt die Assembly oder den Modul Verweis.</span><span class="sxs-lookup"><span data-stu-id="84cdd-109">Receives the assembly or module reference.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84cdd-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="84cdd-110">Return Value</span></span>  
 <span data-ttu-id="84cdd-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="84cdd-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84cdd-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="84cdd-112">Requirements</span></span>  
 <span data-ttu-id="84cdd-113">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="84cdd-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84cdd-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84cdd-114">See also</span></span>

- [<span data-ttu-id="84cdd-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84cdd-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="84cdd-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84cdd-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="84cdd-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="84cdd-117">ALink API</span></span>](index.md)
