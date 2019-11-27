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
ms.openlocfilehash: 6a5b3f1e9bf1444feb73949ef7133fbd9ae35134
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446474"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="b4b9e-102">EnumCustomAttributes-Methode</span><span class="sxs-lookup"><span data-stu-id="b4b9e-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="b4b9e-103">Ruft benutzerdefinierte Attribute auf Assemblyebene ab.</span><span class="sxs-lookup"><span data-stu-id="b4b9e-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4b9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4b9e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4b9e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4b9e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="b4b9e-106">Handle des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="b4b9e-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="b4b9e-107">Typ der aufzuzählenden Attribute.</span><span class="sxs-lookup"><span data-stu-id="b4b9e-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="b4b9e-108">Verwenden Sie `mdTokenNill` für alle Attribute.</span><span class="sxs-lookup"><span data-stu-id="b4b9e-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="b4b9e-109">Empfängt benutzerdefinierte Attribut Token.</span><span class="sxs-lookup"><span data-stu-id="b4b9e-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b4b9e-110">Gibt die Größe `rCustomValues` Arrays an.</span><span class="sxs-lookup"><span data-stu-id="b4b9e-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="b4b9e-111">Empfängt optional die Anzahl der Tokenwerte.</span><span class="sxs-lookup"><span data-stu-id="b4b9e-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4b9e-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b4b9e-112">Return Value</span></span>  
 <span data-ttu-id="b4b9e-113">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="b4b9e-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4b9e-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b4b9e-114">Requirements</span></span>  
 <span data-ttu-id="b4b9e-115">Erfordert "Alink. h"</span><span class="sxs-lookup"><span data-stu-id="b4b9e-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4b9e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4b9e-116">See also</span></span>

- [<span data-ttu-id="b4b9e-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4b9e-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b4b9e-118">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b4b9e-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b4b9e-119">Alink-API</span><span class="sxs-lookup"><span data-stu-id="b4b9e-119">ALink API</span></span>](index.md)
