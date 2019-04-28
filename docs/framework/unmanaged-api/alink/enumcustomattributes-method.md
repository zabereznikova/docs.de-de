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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789973"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="32c85-102">EnumCustomAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="32c85-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="32c85-103">Ruft benutzerdefinierte Attribute auf Assemblyebene.</span><span class="sxs-lookup"><span data-stu-id="32c85-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32c85-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32c85-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="32c85-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="32c85-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="32c85-106">Handle des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="32c85-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="32c85-107">Typ der Attribute aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="32c85-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="32c85-108">Verwendung `mdTokenNill` für alle Attribute.</span><span class="sxs-lookup"><span data-stu-id="32c85-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="32c85-109">Benutzerdefinierte Attribute-Token erhält.</span><span class="sxs-lookup"><span data-stu-id="32c85-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="32c85-110">Gibt die Größe des `rCustomValues` Array.</span><span class="sxs-lookup"><span data-stu-id="32c85-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="32c85-111">Empfängt optional die Anzahl von Tokenwerten.</span><span class="sxs-lookup"><span data-stu-id="32c85-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32c85-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="32c85-112">Return Value</span></span>  
 <span data-ttu-id="32c85-113">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="32c85-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32c85-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="32c85-114">Requirements</span></span>  
 <span data-ttu-id="32c85-115">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="32c85-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c85-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32c85-116">See also</span></span>

- [<span data-ttu-id="32c85-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="32c85-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="32c85-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="32c85-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="32c85-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="32c85-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
