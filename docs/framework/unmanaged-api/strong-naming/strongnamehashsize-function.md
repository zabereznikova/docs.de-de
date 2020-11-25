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
ms.openlocfilehash: 1116fcde754f966a783f4fdca85df8bd3ca1b0ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724428"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="ee47e-102">StrongNameHashSize-Funktion</span><span class="sxs-lookup"><span data-stu-id="ee47e-102">StrongNameHashSize Function</span></span>

<span data-ttu-id="ee47e-103">Ruft mit dem angegebenen Hashalgorithmus die Puffergröße ab, die für einen Hash erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ee47e-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="ee47e-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="ee47e-104">This function has been deprecated.</span></span> <span data-ttu-id="ee47e-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="ee47e-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee47e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee47e-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee47e-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="ee47e-107">Parameters</span></span>  

 `ulHashAlg`  
 <span data-ttu-id="ee47e-108">in Der Hash Algorithmus, der verwendet wird, um die Puffergröße zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="ee47e-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="ee47e-109">vorgenommen Die zurückgegebene Puffergröße in Bytes.</span><span class="sxs-lookup"><span data-stu-id="ee47e-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee47e-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ee47e-110">Return Value</span></span>  

 <span data-ttu-id="ee47e-111">`true` nach erfolgreichem Abschluss: andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="ee47e-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee47e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee47e-112">Remarks</span></span>  

 <span data-ttu-id="ee47e-113">Wenn die `StrongNameHashSize` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ee47e-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee47e-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ee47e-114">Requirements</span></span>  

 <span data-ttu-id="ee47e-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee47e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee47e-116">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="ee47e-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ee47e-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ee47e-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee47e-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee47e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee47e-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee47e-119">See also</span></span>

- [<span data-ttu-id="ee47e-120">StrongNameHashSize-Methode</span><span class="sxs-lookup"><span data-stu-id="ee47e-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="ee47e-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee47e-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
