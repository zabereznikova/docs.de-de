---
title: SetAssemblyProps-Methode
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyProps
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method
ms.assetid: a3d7cf29-1414-49e6-8aae-9b3283c4f5f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1e9f51799ea56cb1e5819d708a0e4a8136a94f3d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741491"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="af7a9-102">SetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="af7a9-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="af7a9-103">Weist Eigenschaften auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="af7a9-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af7a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af7a9-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="af7a9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="af7a9-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="af7a9-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="af7a9-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="af7a9-107">Datei, die Eigenschaft definiert.</span><span class="sxs-lookup"><span data-stu-id="af7a9-107">File that defines the property.</span></span> <span data-ttu-id="af7a9-108">Kann NULL sein, wenn `AssemblyID` gibt nicht an eine nicht gebundene NETMODULE-Datei.</span><span class="sxs-lookup"><span data-stu-id="af7a9-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="af7a9-109">Gibt an, die Möglichkeit, zu ändern.</span><span class="sxs-lookup"><span data-stu-id="af7a9-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="af7a9-110">Neue Wert der Option.</span><span class="sxs-lookup"><span data-stu-id="af7a9-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af7a9-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="af7a9-111">Return Value</span></span>  
 <span data-ttu-id="af7a9-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="af7a9-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af7a9-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af7a9-113">Requirements</span></span>  
 <span data-ttu-id="af7a9-114">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="af7a9-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af7a9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af7a9-115">See also</span></span>

- [<span data-ttu-id="af7a9-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af7a9-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="af7a9-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af7a9-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="af7a9-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="af7a9-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
