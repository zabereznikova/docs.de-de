---
title: SetAssemblyProps-Methode
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae13daab0352ad4367c7ad6e06d6c12af23c75bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="setassemblyprops-method"></a><span data-ttu-id="63b31-102">SetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="63b31-102">SetAssemblyProps Method</span></span>
<span data-ttu-id="63b31-103">Weist Eigenschaften auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="63b31-103">Assigns assembly-level properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63b31-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63b31-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyProps(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    AssemblyOptions Option,  
    VARIANT         Value  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63b31-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="63b31-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="63b31-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="63b31-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="63b31-107">Datei, die die Eigenschaft definiert.</span><span class="sxs-lookup"><span data-stu-id="63b31-107">File that defines the property.</span></span> <span data-ttu-id="63b31-108">Kann NULL sein, wenn `AssemblyID` einen ungebundenen NETMODULE-Datei nicht an.</span><span class="sxs-lookup"><span data-stu-id="63b31-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `Option`  
 <span data-ttu-id="63b31-109">Gibt an, die Möglichkeit zum Ändern.</span><span class="sxs-lookup"><span data-stu-id="63b31-109">Indicates the option to modify.</span></span>  
  
 `Value`  
 <span data-ttu-id="63b31-110">Neuer Wert der Option.</span><span class="sxs-lookup"><span data-stu-id="63b31-110">New value of the option.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63b31-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="63b31-111">Return Value</span></span>  
 <span data-ttu-id="63b31-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="63b31-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63b31-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63b31-113">Requirements</span></span>  
 <span data-ttu-id="63b31-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="63b31-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63b31-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63b31-115">See Also</span></span>  
 [<span data-ttu-id="63b31-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63b31-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="63b31-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63b31-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="63b31-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="63b31-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
