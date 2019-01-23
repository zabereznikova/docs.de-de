---
title: EnumImportTypes-Methode
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e437868138d7ae31d233853ecc0f709de3ee39d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512722"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="8812c-102">EnumImportTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="8812c-102">EnumImportTypes Method</span></span>
<span data-ttu-id="8812c-103">Listet jeden Typ in jedem Bereich an.</span><span class="sxs-lookup"><span data-stu-id="8812c-103">Enumerates each type in each scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8812c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8812c-104">Syntax</span></span>  
  
```  
HRESULT EnumImportTypes(  
    HALINKENUM   hEnum,  
    DWORD        dwMax,  
    mdTypeDef    aTypeDefs[],  
    DWORD*       pdwCount  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8812c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8812c-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="8812c-106">Handle für Enumerator.</span><span class="sxs-lookup"><span data-stu-id="8812c-106">Handle for enumerator.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="8812c-107">Maximale Anzahl von Typen, die abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8812c-107">Maximum number of types to retrieve.</span></span>  
  
 `aTypeDefs`  
 <span data-ttu-id="8812c-108">Empfängt Typtoken, nicht zu überschreiten `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="8812c-108">Recieves type tokens, not to exceed `dwMax`.</span></span>  
  
 `pdwCount`  
 <span data-ttu-id="8812c-109">Empfängt die tatsächliche Anzahl der Typen in `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="8812c-109">Receives actual number of type in `aTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8812c-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8812c-110">Return Value</span></span>  
 <span data-ttu-id="8812c-111">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="8812c-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8812c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8812c-112">Requirements</span></span>  
 <span data-ttu-id="8812c-113">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="8812c-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8812c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8812c-114">See also</span></span>
- [<span data-ttu-id="8812c-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8812c-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="8812c-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8812c-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="8812c-117">Alink-API</span><span class="sxs-lookup"><span data-stu-id="8812c-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
