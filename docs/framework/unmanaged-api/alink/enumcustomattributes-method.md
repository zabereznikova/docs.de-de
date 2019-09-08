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
ms.openlocfilehash: 5d8827f46a12bd090fa27e71072d833607d34677
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777347"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="5ce7f-102">EnumCustomAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="5ce7f-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="5ce7f-103">Ruft benutzerdefinierte Attribute auf Assemblyebene ab.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ce7f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ce7f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ce7f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ce7f-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="5ce7f-106">Handle des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="5ce7f-107">Typ der aufzuzählenden Attribute.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="5ce7f-108">Verwenden `mdTokenNill` Sie für alle Attribute.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="5ce7f-109">Empfängt benutzerdefinierte Attribut Token.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5ce7f-110">Gibt die Größe `rCustomValues` des Arrays an.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="5ce7f-111">Empfängt optional die Anzahl der Tokenwerte.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ce7f-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5ce7f-112">Return Value</span></span>  
 <span data-ttu-id="5ce7f-113">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="5ce7f-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ce7f-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ce7f-114">Requirements</span></span>  
 <span data-ttu-id="5ce7f-115">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="5ce7f-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ce7f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ce7f-116">See also</span></span>

- [<span data-ttu-id="5ce7f-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ce7f-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5ce7f-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ce7f-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5ce7f-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="5ce7f-119">ALink API</span></span>](index.md)
