---
title: EnumCustomAttributes-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location: alink.dll
api_type: COM
f1_keywords: EnumCustomAttributes
helpviewer_keywords: EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d616babb47ac0282ef56d119ab448a94fd24c7c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="6dac0-102">EnumCustomAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="6dac0-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="6dac0-103">Ruft benutzerdefinierte Attribute auf Assemblyebene ab.</span><span class="sxs-lookup"><span data-stu-id="6dac0-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dac0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6dac0-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6dac0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6dac0-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="6dac0-106">Das Handle des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="6dac0-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="6dac0-107">Typ der Attribute aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6dac0-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="6dac0-108">Verwendung `mdTokenNill` für alle Attribute.</span><span class="sxs-lookup"><span data-stu-id="6dac0-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="6dac0-109">Benutzerdefinierte Attribute Token erhält.</span><span class="sxs-lookup"><span data-stu-id="6dac0-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6dac0-110">Gibt die Größe des `rCustomValues` Array.</span><span class="sxs-lookup"><span data-stu-id="6dac0-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="6dac0-111">Empfängt optional die Anzahl von Tokenwerten.</span><span class="sxs-lookup"><span data-stu-id="6dac0-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6dac0-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6dac0-112">Return Value</span></span>  
 <span data-ttu-id="6dac0-113">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6dac0-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dac0-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6dac0-114">Requirements</span></span>  
 <span data-ttu-id="6dac0-115">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="6dac0-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dac0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6dac0-116">See Also</span></span>  
 [<span data-ttu-id="6dac0-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6dac0-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="6dac0-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6dac0-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="6dac0-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="6dac0-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
