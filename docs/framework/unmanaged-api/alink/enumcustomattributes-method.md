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
ms.openlocfilehash: febaba5155753e9d60a3708582f4f58bd7861ec7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="db154-102">EnumCustomAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="db154-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="db154-103">Ruft benutzerdefinierte Attribute auf Assemblyebene ab.</span><span class="sxs-lookup"><span data-stu-id="db154-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db154-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db154-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db154-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="db154-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="db154-106">Das Handle des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="db154-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="db154-107">Typ der Attribute aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="db154-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="db154-108">Verwendung `mdTokenNill` für alle Attribute.</span><span class="sxs-lookup"><span data-stu-id="db154-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="db154-109">Benutzerdefinierte Attribute Token erhält.</span><span class="sxs-lookup"><span data-stu-id="db154-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="db154-110">Gibt die Größe des `rCustomValues` Array.</span><span class="sxs-lookup"><span data-stu-id="db154-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="db154-111">Empfängt optional die Anzahl von Tokenwerten.</span><span class="sxs-lookup"><span data-stu-id="db154-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db154-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="db154-112">Return Value</span></span>  
 <span data-ttu-id="db154-113">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="db154-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db154-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db154-114">Requirements</span></span>  
 <span data-ttu-id="db154-115">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="db154-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db154-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db154-116">See Also</span></span>  
 [<span data-ttu-id="db154-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db154-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="db154-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db154-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="db154-119">ALink-API</span><span class="sxs-lookup"><span data-stu-id="db154-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
