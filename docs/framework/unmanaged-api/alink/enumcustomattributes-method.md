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
ms.openlocfilehash: 445c833d10631341ef7ad579eaff8ddd96be3428
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684849"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="1b544-102">EnumCustomAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="1b544-102">EnumCustomAttributes Method</span></span>

<span data-ttu-id="1b544-103">Ruft benutzerdefinierte Attribute auf Assemblyebene ab.</span><span class="sxs-lookup"><span data-stu-id="1b544-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b544-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b544-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b544-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1b544-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="1b544-106">Handle des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="1b544-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="1b544-107">Typ der aufzuzählenden Attribute.</span><span class="sxs-lookup"><span data-stu-id="1b544-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="1b544-108">Verwenden Sie `mdTokenNill` für alle Attribute.</span><span class="sxs-lookup"><span data-stu-id="1b544-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="1b544-109">Empfängt benutzerdefinierte Attribut Token.</span><span class="sxs-lookup"><span data-stu-id="1b544-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1b544-110">Gibt die Größe des `rCustomValues` Arrays an.</span><span class="sxs-lookup"><span data-stu-id="1b544-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="1b544-111">Empfängt optional die Anzahl der Tokenwerte.</span><span class="sxs-lookup"><span data-stu-id="1b544-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b544-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1b544-112">Return Value</span></span>  

 <span data-ttu-id="1b544-113">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="1b544-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b544-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1b544-114">Requirements</span></span>  

 <span data-ttu-id="1b544-115">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="1b544-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b544-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b544-116">See also</span></span>

- [<span data-ttu-id="1b544-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b544-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="1b544-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1b544-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="1b544-119">ALink-API</span><span class="sxs-lookup"><span data-stu-id="1b544-119">ALink API</span></span>](index.md)
