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
ms.openlocfilehash: 04103ad305e0ae97669f3e07e06f03c2cdb4dfbd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787522"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="f55b6-102">EmitInternalExportedTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="f55b6-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="f55b6-103">Gibt Typen aus, die der Assembly hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f55b6-103">Emits types added to the assembly.</span></span> <span data-ttu-id="f55b6-104">Ruft diese Methode auf, nachdem bekannte interne Typen hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="f55b6-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f55b6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f55b6-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f55b6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f55b6-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f55b6-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="f55b6-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f55b6-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f55b6-108">Return Value</span></span>  
 <span data-ttu-id="f55b6-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="f55b6-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f55b6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f55b6-110">Requirements</span></span>  
 <span data-ttu-id="f55b6-111">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="f55b6-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f55b6-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f55b6-112">See also</span></span>

- [<span data-ttu-id="f55b6-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f55b6-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f55b6-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f55b6-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f55b6-115">Alink-API</span><span class="sxs-lookup"><span data-stu-id="f55b6-115">ALink API</span></span>](index.md)
