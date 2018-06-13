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
ms.openlocfilehash: 5a3d7d3bb05a878f4d9832cf39a8e8863929c4e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403213"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="978c9-102">EnumCustomAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="978c9-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="978c9-103">Ruft benutzerdefinierte Attribute auf Assemblyebene ab.</span><span class="sxs-lookup"><span data-stu-id="978c9-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="978c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="978c9-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="978c9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="978c9-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="978c9-106">Das Handle des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="978c9-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="978c9-107">Typ der Attribute aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="978c9-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="978c9-108">Verwendung `mdTokenNill` für alle Attribute.</span><span class="sxs-lookup"><span data-stu-id="978c9-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="978c9-109">Benutzerdefinierte Attribute Token erhält.</span><span class="sxs-lookup"><span data-stu-id="978c9-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="978c9-110">Gibt die Größe des `rCustomValues` Array.</span><span class="sxs-lookup"><span data-stu-id="978c9-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="978c9-111">Empfängt optional die Anzahl von Tokenwerten.</span><span class="sxs-lookup"><span data-stu-id="978c9-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="978c9-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="978c9-112">Return Value</span></span>  
 <span data-ttu-id="978c9-113">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="978c9-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="978c9-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="978c9-114">Requirements</span></span>  
 <span data-ttu-id="978c9-115">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="978c9-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="978c9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="978c9-116">See Also</span></span>  
 [<span data-ttu-id="978c9-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="978c9-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="978c9-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="978c9-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="978c9-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="978c9-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
