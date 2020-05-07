---
title: _EFN_GetManagedObjectName-Funktion
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
ms.openlocfilehash: 708ac2e407bf6f87dbe314a0e87cdd16f45b2bcf
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860753"
---
# <a name="_efn_getmanagedobjectname-function"></a><span data-ttu-id="a7a76-102">\_EFN\_getmanagedobjectname-Funktion</span><span class="sxs-lookup"><span data-stu-id="a7a76-102">\_EFN\_GetManagedObjectName Function</span></span>
<span data-ttu-id="a7a76-103">Ruft den Namen eines Typs mithilfe des bereitgestellten verwalteten Objekt Zeigers ab.</span><span class="sxs-lookup"><span data-stu-id="a7a76-103">Gets the name of a type using the provided managed object pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7a76-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7a76-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7a76-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7a76-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="a7a76-106">in Ein Zeiger auf den Debugclient.</span><span class="sxs-lookup"><span data-stu-id="a7a76-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="a7a76-107">in Ein Zeiger für verwaltete Objekte.</span><span class="sxs-lookup"><span data-stu-id="a7a76-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="a7a76-108">szName</span><span class="sxs-lookup"><span data-stu-id="a7a76-108">szName</span></span>  
 <span data-ttu-id="a7a76-109">vorgenommen Der Name des Typs.</span><span class="sxs-lookup"><span data-stu-id="a7a76-109">[out] The name of the type.</span></span>  
  
 `cbName`  
 <span data-ttu-id="a7a76-110">vorgenommen Die Anzahl von Zeichen, die im Zeichen folgen Puffer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a7a76-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7a76-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7a76-111">Remarks</span></span>  
 <span data-ttu-id="a7a76-112">Wenn im Thread derzeit kein verwalteter Code vorhanden ist, gibt die Funktion HRESULT SOS_E_NOMANAGEDCODE mit einem Einrichtungs Wert von 0xa0 und dem Fehlercode 0x1000 zurück.</span><span class="sxs-lookup"><span data-stu-id="a7a76-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7a76-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7a76-113">Requirements</span></span>  
 <span data-ttu-id="a7a76-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7a76-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7a76-115">**Header:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="a7a76-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="a7a76-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7a76-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a76-117">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a7a76-117">See also</span></span>

- [<span data-ttu-id="a7a76-118">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="a7a76-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
