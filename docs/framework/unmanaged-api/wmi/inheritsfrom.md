---
title: InheritsFrom-Funktion (Referenz zur nicht verwalteten API)
description: Die InheritsFrom-Funktion bestimmt, ob eine Klasse oder Instanz aus einer bestimmten übergeordneten Klasse abgeleitet ist.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d2af1b41f47a3906c0e573c104847aa3ff36cf8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158430"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="631d0-103">InheritsFrom-Funktion</span><span class="sxs-lookup"><span data-stu-id="631d0-103">InheritsFrom function</span></span>
<span data-ttu-id="631d0-104">Bestimmt, ob die aktuelle Klasse oder Instanz aus einer angegebenen übergeordneten Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="631d0-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="631d0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="631d0-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="631d0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="631d0-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="631d0-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="631d0-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="631d0-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="631d0-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="631d0-109">[in] Der Name der Klasse.</span><span class="sxs-lookup"><span data-stu-id="631d0-109">[in] The name of the class.</span></span> `wszAncestor` <span data-ttu-id="631d0-110">muss auf einen gültigen zeigen `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="631d0-110">must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="631d0-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="631d0-111">Return value</span></span>

<span data-ttu-id="631d0-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="631d0-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="631d0-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="631d0-113">Constant</span></span>  |<span data-ttu-id="631d0-114">Wert</span><span class="sxs-lookup"><span data-stu-id="631d0-114">Value</span></span>  |<span data-ttu-id="631d0-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="631d0-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="631d0-116">0</span><span class="sxs-lookup"><span data-stu-id="631d0-116">0</span></span> | <span data-ttu-id="631d0-117">Das aktuelle Objekt erbt `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="631d0-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="631d0-118">1</span><span class="sxs-lookup"><span data-stu-id="631d0-118">1</span></span> | <span data-ttu-id="631d0-119">Das aktuelle Objekt erbt nicht von `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="631d0-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="631d0-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="631d0-120">0x80041008</span></span> | `wszAncestor` <span data-ttu-id="631d0-121">is `null`.</span><span class="sxs-lookup"><span data-stu-id="631d0-121">is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="631d0-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="631d0-122">Remarks</span></span>

<span data-ttu-id="631d0-123">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) Methode.</span><span class="sxs-lookup"><span data-stu-id="631d0-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="631d0-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="631d0-124">Requirements</span></span>  
 <span data-ttu-id="631d0-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="631d0-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="631d0-126">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="631d0-126">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="631d0-127">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="631d0-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="631d0-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="631d0-128">See also</span></span>

- [<span data-ttu-id="631d0-129">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="631d0-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
