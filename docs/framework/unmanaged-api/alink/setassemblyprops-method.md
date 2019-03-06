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
ms.openlocfilehash: dc9ca5d9533a6c4a297155a47ac0061f1232d242
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481101"
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="f98be-102">SetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="f98be-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="f98be-103">Weist Eigenschaften auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="f98be-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f98be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f98be-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f98be-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f98be-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f98be-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="f98be-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f98be-107">Datei, die Eigenschaft definiert.</span><span class="sxs-lookup"><span data-stu-id="f98be-107">File that defines the property.</span></span> <span data-ttu-id="f98be-108">Kann NULL sein, wenn `AssemblyID` gibt nicht an eine nicht gebundene NETMODULE-Datei.</span><span class="sxs-lookup"><span data-stu-id="f98be-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="f98be-109">Gibt an, die Möglichkeit, zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f98be-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="f98be-110">Neue Wert der Option.</span><span class="sxs-lookup"><span data-stu-id="f98be-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f98be-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f98be-111">Return Value</span></span>  
 <span data-ttu-id="f98be-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="f98be-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f98be-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f98be-113">Requirements</span></span>  
 <span data-ttu-id="f98be-114">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="f98be-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f98be-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f98be-115">See also</span></span>
- [<span data-ttu-id="f98be-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f98be-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f98be-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f98be-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f98be-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="f98be-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
