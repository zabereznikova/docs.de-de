---
title: EnumCustomAttributes-Methode
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b419962982fc80591ed565cceb28afb88a39495e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199140"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="f261d-102">EnumCustomAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="f261d-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="f261d-103">Ruft benutzerdefinierte Attribute auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="f261d-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f261d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f261d-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f261d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f261d-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="f261d-106">Handle des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="f261d-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="f261d-107">Typ der Attribute aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f261d-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="f261d-108">Verwendung `mdTokenNill` für alle Attribute.</span><span class="sxs-lookup"><span data-stu-id="f261d-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="f261d-109">Benutzerdefinierte Attribute-Token erhält.</span><span class="sxs-lookup"><span data-stu-id="f261d-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f261d-110">Gibt die Größe des `rCustomValues` Array.</span><span class="sxs-lookup"><span data-stu-id="f261d-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="f261d-111">Empfängt optional die Anzahl von Tokenwerten.</span><span class="sxs-lookup"><span data-stu-id="f261d-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f261d-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f261d-112">Return Value</span></span>  
 <span data-ttu-id="f261d-113">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="f261d-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f261d-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f261d-114">Requirements</span></span>  
 <span data-ttu-id="f261d-115">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="f261d-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f261d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f261d-116">See also</span></span>

- [<span data-ttu-id="f261d-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f261d-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f261d-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f261d-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f261d-119">ALink-API</span><span class="sxs-lookup"><span data-stu-id="f261d-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
