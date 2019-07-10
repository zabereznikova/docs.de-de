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
ms.openlocfilehash: 15174480c4345f2514572701a5525f0f192ad120
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742101"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="9dc2c-102">EmitInternalExportedTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="9dc2c-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="9dc2c-103">Gibt die Typen, die hinzugefügt werden, auf die Assembly aus.</span><span class="sxs-lookup"><span data-stu-id="9dc2c-103">Emits types added to the assembly.</span></span> <span data-ttu-id="9dc2c-104">Rufen Sie diese Methode aus, nachdem bekannt, dass die interne Typen hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="9dc2c-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dc2c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9dc2c-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dc2c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9dc2c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9dc2c-107">ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="9dc2c-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9dc2c-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9dc2c-108">Return Value</span></span>  
 <span data-ttu-id="9dc2c-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="9dc2c-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dc2c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9dc2c-110">Requirements</span></span>  
 <span data-ttu-id="9dc2c-111">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="9dc2c-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dc2c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dc2c-112">See also</span></span>

- [<span data-ttu-id="9dc2c-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9dc2c-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="9dc2c-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9dc2c-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="9dc2c-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="9dc2c-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
