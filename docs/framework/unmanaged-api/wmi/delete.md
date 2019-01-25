---
title: Delete-Funktion (Referenz zur nicht verwalteten API)
description: Die Löschfunktion löscht die angegebene Eigenschaft und aller seiner Qualifizierer aus der Definition einer CIM-Klasse.
ms.date: 11/06/2017
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
ms.openlocfilehash: 0590c639e7cc6622c2283bfa609ccb31d7ce7e2b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720573"
---
# <a name="delete-function"></a><span data-ttu-id="56345-103">Delete-Funktion</span><span class="sxs-lookup"><span data-stu-id="56345-103">Delete function</span></span>
<span data-ttu-id="56345-104">Löscht die angegebene Eigenschaft und aller seiner Qualifizierer aus der Definition einer CIM-Klasse an.</span><span class="sxs-lookup"><span data-stu-id="56345-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="56345-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="56345-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="56345-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="56345-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="56345-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="56345-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="56345-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="56345-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="56345-109">[in] Der Name des zu löschenden Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="56345-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="56345-110">`wszName` muss ein Zeiger auf ein gültiges `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="56345-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="56345-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="56345-111">Return value</span></span>

<span data-ttu-id="56345-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="56345-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="56345-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="56345-113">Constant</span></span>  |<span data-ttu-id="56345-114">Wert</span><span class="sxs-lookup"><span data-stu-id="56345-114">Value</span></span>  |<span data-ttu-id="56345-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="56345-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="56345-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="56345-116">0x80041001</span></span> | <span data-ttu-id="56345-117">Ein Unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="56345-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="56345-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="56345-118">0x80041016</span></span> | <span data-ttu-id="56345-119">Die Eigenschaft kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="56345-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="56345-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="56345-120">0x80041008</span></span> | <span data-ttu-id="56345-121">`wszzName` ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="56345-121">`wszzName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="56345-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="56345-122">0x80041002</span></span> | <span data-ttu-id="56345-123">Die angegebene Eigenschaft ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="56345-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="56345-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="56345-124">0x80041006</span></span> | <span data-ttu-id="56345-125">Es ist nicht genügend Arbeitsspeicher zum Abschließen des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="56345-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="56345-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="56345-126">0x8004101c</span></span> | <span data-ttu-id="56345-127">Die Eigenschaft wird von einer Basisklasse geerbt.</span><span class="sxs-lookup"><span data-stu-id="56345-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="56345-128">Die Eigenschaft ist eine Systemeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="56345-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="56345-129">0</span><span class="sxs-lookup"><span data-stu-id="56345-129">0</span></span> | <span data-ttu-id="56345-130">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="56345-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="56345-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="56345-131">0x80041030</span></span> | <span data-ttu-id="56345-132">Die Funktion gelöscht einen Standardwert außer Kraft setzen, für die aktuelle Klasse.</span><span class="sxs-lookup"><span data-stu-id="56345-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="56345-133">Der Standardwert für diese Eigenschaft in der übergeordneten Klasse wurde Reactiviated.</span><span class="sxs-lookup"><span data-stu-id="56345-133">The default value for this property in the parent class has been reactiviated.</span></span> | 

## <a name="remarks"></a><span data-ttu-id="56345-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="56345-134">Remarks</span></span>

<span data-ttu-id="56345-135">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) Methode.</span><span class="sxs-lookup"><span data-stu-id="56345-135">This function wraps a call to the [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="56345-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="56345-136">Requirements</span></span>  
 <span data-ttu-id="56345-137">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56345-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56345-138">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="56345-138">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="56345-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="56345-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56345-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56345-140">See also</span></span>
- [<span data-ttu-id="56345-141">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="56345-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
