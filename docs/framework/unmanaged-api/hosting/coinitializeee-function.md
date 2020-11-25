---
title: CoInitializeEE-Funktion
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
ms.openlocfilehash: 707e182e62f4a7b7b813e6b288c6825b0d3d2eab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731748"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="e4973-102">CoInitializeEE-Funktion</span><span class="sxs-lookup"><span data-stu-id="e4973-102">CoInitializeEE Function</span></span>

<span data-ttu-id="e4973-103">Stellt sicher, dass die Common Language Runtime Ausführungs-Engine in einen Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="e4973-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="e4973-104">Diese Funktion ist in der .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="e4973-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="e4973-105">Verwenden Sie stattdessen die [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="e4973-105">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4973-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4973-106">Syntax</span></span>  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4973-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4973-107">Parameters</span></span>  

 `fFlags`  
 <span data-ttu-id="e4973-108">in Eine der [COINITIEE](../metadata/coinitiee-enumeration.md) -Enumerationskonstanten.</span><span class="sxs-lookup"><span data-stu-id="e4973-108">[in] One of the [COINITIEE](../metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4973-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e4973-109">Return Value</span></span>  

 <span data-ttu-id="e4973-110">Diese Methode gibt in WinError. h definierte Standard-COM-Fehlercodes und die Werte in der folgenden Tabelle zurück.</span><span class="sxs-lookup"><span data-stu-id="e4973-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="e4973-111">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="e4973-111">Return code</span></span>|<span data-ttu-id="e4973-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e4973-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="e4973-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e4973-113">S_OK</span></span>|<span data-ttu-id="e4973-114">Die Ausführungs-Engine wurde erfolgreich geladen.</span><span class="sxs-lookup"><span data-stu-id="e4973-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="e4973-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e4973-115">S_FALSE</span></span>|<span data-ttu-id="e4973-116">Die Ausführungs-Engine ist bereits geladen.</span><span class="sxs-lookup"><span data-stu-id="e4973-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="e4973-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e4973-117">E_FAIL</span></span>|<span data-ttu-id="e4973-118">Die Ausführungs-Engine konnte nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="e4973-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4973-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4973-119">Remarks</span></span>  

 <span data-ttu-id="e4973-120">Diese Methode lädt die Ausführungs-Engine, wenn Sie noch nicht geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="e4973-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4973-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e4973-121">Requirements</span></span>  

 <span data-ttu-id="e4973-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4973-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4973-123">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e4973-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e4973-124">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e4973-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e4973-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4973-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4973-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e4973-126">See also</span></span>

- [<span data-ttu-id="e4973-127">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="e4973-127">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
