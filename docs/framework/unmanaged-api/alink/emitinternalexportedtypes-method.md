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
ms.openlocfilehash: c196bcc159b18b9dc04329d817ebe16e07bb8bb7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218250"
---
# <a name="emitinternalexportedtypes-method"></a><span data-ttu-id="b18e1-102">EmitInternalExportedTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="b18e1-102">EmitInternalExportedTypes Method</span></span>
<span data-ttu-id="b18e1-103">Gibt die Typen, die hinzugefügt werden, auf die Assembly aus.</span><span class="sxs-lookup"><span data-stu-id="b18e1-103">Emits types added to the assembly.</span></span> <span data-ttu-id="b18e1-104">Rufen Sie diese Methode aus, nachdem bekannt, dass die interne Typen hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="b18e1-104">Call this method after known internal types have been added.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b18e1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b18e1-105">Syntax</span></span>  
  
```  
HRESULT EmitInternalExportedTypes(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b18e1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b18e1-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b18e1-107">ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="b18e1-107">ID of assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b18e1-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b18e1-108">Return Value</span></span>  
 <span data-ttu-id="b18e1-109">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="b18e1-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b18e1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b18e1-110">Requirements</span></span>  
 <span data-ttu-id="b18e1-111">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="b18e1-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b18e1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b18e1-112">See also</span></span>

- [<span data-ttu-id="b18e1-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b18e1-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b18e1-114">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b18e1-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b18e1-115">ALink-API</span><span class="sxs-lookup"><span data-stu-id="b18e1-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
