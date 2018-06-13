---
title: EmitInternalExportedTypes-Methode
ms.date: 03/30/2017
api_name:
- EmitInternalExportedTypes
- IALink2.EmitInternalExportedTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitInternalExportedTypes
helpviewer_keywords:
- EmitInternalExportedTypes method
ms.assetid: 28c8b00d-2c14-40b4-aed5-a1db0e2428eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 55b9d185804f25c7431f2696d67753cc3ba02d1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402040"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="f7b60-102">EmitInternalExportedTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="f7b60-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="f7b60-103">Gibt die Typen, die auf die Assembly hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f7b60-103">Emits types added to the assembly.</span></span> <span data-ttu-id="f7b60-104">Rufen Sie diese Methode, nachdem bekannt, dass die interne Typen hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="f7b60-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7b60-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7b60-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7b60-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f7b60-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f7b60-107">ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="f7b60-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7b60-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f7b60-108">Return Value</span></span>  
 <span data-ttu-id="f7b60-109">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7b60-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7b60-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f7b60-110">Requirements</span></span>  
 <span data-ttu-id="f7b60-111">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="f7b60-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b60-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7b60-112">See Also</span></span>  
 [<span data-ttu-id="f7b60-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7b60-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="f7b60-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7b60-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="f7b60-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="f7b60-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
