---
title: StrongNameHashSize-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameHashSize
helpviewer_keywords:
- StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type:
- apiref
ms.openlocfilehash: c656f73748faf8be7124be65f3ed455f2d5fd07a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105191"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="656bc-102">StrongNameHashSize-Funktion</span><span class="sxs-lookup"><span data-stu-id="656bc-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="656bc-103">Ruft mit dem angegebenen Hashalgorithmus die Puffergröße ab, die für einen Hash erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="656bc-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="656bc-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="656bc-104">This function has been deprecated.</span></span> <span data-ttu-id="656bc-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="656bc-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="656bc-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="656bc-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="656bc-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="656bc-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="656bc-108">in Der Hash Algorithmus, der verwendet wird, um die Puffergröße zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="656bc-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="656bc-109">vorgenommen Die zurückgegebene Puffergröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="656bc-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="656bc-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="656bc-110">Return Value</span></span>  
 <span data-ttu-id="656bc-111">`true` nach erfolgreichem Abschluss. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="656bc-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="656bc-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="656bc-112">Remarks</span></span>  
 <span data-ttu-id="656bc-113">Wenn die `StrongNameHashSize`-Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="656bc-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="656bc-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="656bc-114">Requirements</span></span>  
 <span data-ttu-id="656bc-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="656bc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="656bc-116">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="656bc-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="656bc-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="656bc-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="656bc-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="656bc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="656bc-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="656bc-119">See also</span></span>

- [<span data-ttu-id="656bc-120">StrongNameHashSize-Methode</span><span class="sxs-lookup"><span data-stu-id="656bc-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="656bc-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="656bc-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
