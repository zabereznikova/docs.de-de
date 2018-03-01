---
title: "Löschfunktion (Referenz zur nicht verwalteten API)"
description: "Die Delete-Funktion löscht die angegebene Eigenschaft und alle seine Qualifizierer aus der Definition einer CIM-Klasse."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30f5bf651990cafe06811019cf2b3d92f866f646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="delete-function"></a><span data-ttu-id="aa187-103">Löschen Sie-Funktion</span><span class="sxs-lookup"><span data-stu-id="aa187-103">Delete function</span></span>
<span data-ttu-id="aa187-104">Löscht die angegebene Eigenschaft und aller seiner Qualifizierer aus der Definition einer CIM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="aa187-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="aa187-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa187-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="aa187-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa187-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="aa187-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa187-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="aa187-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="aa187-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="aa187-109">[in] Der Name des zu löschenden Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="aa187-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="aa187-110">`wszName`muss ein Zeiger auf eine gültige `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="aa187-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="aa187-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="aa187-111">Return value</span></span>

<span data-ttu-id="aa187-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="aa187-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="aa187-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="aa187-113">Constant</span></span>  |<span data-ttu-id="aa187-114">Wert</span><span class="sxs-lookup"><span data-stu-id="aa187-114">Value</span></span>  |<span data-ttu-id="aa187-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa187-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="aa187-116">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="aa187-116">0x80041001</span></span> | <span data-ttu-id="aa187-117">Nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="aa187-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="aa187-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="aa187-118">0x80041016</span></span> | <span data-ttu-id="aa187-119">Die Eigenschaft kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="aa187-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="aa187-120">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="aa187-120">0x80041008</span></span> | <span data-ttu-id="aa187-121">`wszzName` ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="aa187-121">`wszzName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="aa187-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="aa187-122">0x80041002</span></span> | <span data-ttu-id="aa187-123">Die angegebene Eigenschaft ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="aa187-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="aa187-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="aa187-124">0x80041006</span></span> | <span data-ttu-id="aa187-125">Es ist nicht genügend Arbeitsspeicher zum Abschließen des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="aa187-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="aa187-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="aa187-126">0x8004101c</span></span> | <span data-ttu-id="aa187-127">Die Eigenschaft wird von einer Basisklasse geerbt.</span><span class="sxs-lookup"><span data-stu-id="aa187-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="aa187-128">Die Eigenschaft ist eine Systemeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="aa187-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="aa187-129">0</span><span class="sxs-lookup"><span data-stu-id="aa187-129">0</span></span> | <span data-ttu-id="aa187-130">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="aa187-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="aa187-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="aa187-131">0x80041030</span></span> | <span data-ttu-id="aa187-132">Die Funktion gelöscht einen Standardwert überschreiben für die aktuelle Klasse.</span><span class="sxs-lookup"><span data-stu-id="aa187-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="aa187-133">Der Standardwert für diese Eigenschaft in der übergeordneten Klasse wurde Reactiviated.</span><span class="sxs-lookup"><span data-stu-id="aa187-133">The default value for this property in the parent class has been reactiviated.</span></span> | 

## <a name="remarks"></a><span data-ttu-id="aa187-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa187-134">Remarks</span></span>

<span data-ttu-id="aa187-135">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="aa187-135">This function wraps a call to the [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="aa187-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa187-136">Requirements</span></span>  
 <span data-ttu-id="aa187-137">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa187-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa187-138">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="aa187-138">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="aa187-139">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="aa187-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa187-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa187-140">See also</span></span>  
[<span data-ttu-id="aa187-141">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="aa187-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
