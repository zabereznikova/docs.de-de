---
title: QualifierSet_Delete-Funktion (Referenz zur nicht verwalteten API)
description: "Die Funktion QualifierSet_Delete Löscht einen Qualifizierer anhand des Namens."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Delete
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Delete
helpviewer_keywords: QualifierSet_Delete function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9245fc0ee109837249f1f3df400385c117a2f2d7
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetdelete-function"></a><span data-ttu-id="74c6f-103">QualifierSet_Delete-Funktion</span><span class="sxs-lookup"><span data-stu-id="74c6f-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="74c6f-104">Löscht einen angegebenen Qualifizierer anhand des Namens an.</span><span class="sxs-lookup"><span data-stu-id="74c6f-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="74c6f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="74c6f-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a><span data-ttu-id="74c6f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="74c6f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="74c6f-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="74c6f-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="74c6f-108">[in] Ein Zeiger auf ein [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="74c6f-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="74c6f-109">[in] Der Name des Qualifizierers der gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="74c6f-109">[in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="74c6f-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="74c6f-110">Return value</span></span>

<span data-ttu-id="74c6f-111">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="74c6f-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="74c6f-112">Konstante</span><span class="sxs-lookup"><span data-stu-id="74c6f-112">Constant</span></span>  |<span data-ttu-id="74c6f-113">Wert</span><span class="sxs-lookup"><span data-stu-id="74c6f-113">Value</span></span>  |<span data-ttu-id="74c6f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74c6f-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="74c6f-115">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="74c6f-115">0x80041008</span></span> | <span data-ttu-id="74c6f-116">Die `wszName` -Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="74c6f-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="74c6f-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="74c6f-117">0x80041016</span></span> | <span data-ttu-id="74c6f-118">Durch das Löschen dieses Qualifizierers ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="74c6f-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="74c6f-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="74c6f-119">0x80041002</span></span> | <span data-ttu-id="74c6f-120">Der angegebene Qualifizierer wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="74c6f-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="74c6f-121">0</span><span class="sxs-lookup"><span data-stu-id="74c6f-121">0</span></span> | <span data-ttu-id="74c6f-122">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="74c6f-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="74c6f-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="74c6f-123">0x40002</span></span> | <span data-ttu-id="74c6f-124">Die lokale Außerkraftsetzung wurde gelöscht, und der ursprüngliche Qualifizierer vom übergeordneten Objekt wurde Bereich fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="74c6f-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="74c6f-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74c6f-125">Remarks</span></span>

<span data-ttu-id="74c6f-126">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemQualifierSet::Delete](https://msdn.microsoft.com/library/aa391864(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="74c6f-126">This function wraps a call to the [IWbemQualifierSet::Delete](https://msdn.microsoft.com/library/aa391864(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="74c6f-127">Aufgrund der Qualifizierer Weitergabe Regeln ein bestimmter Qualifizierer möglicherweise wurde von einem anderen Objekt geerbt und lediglich in der aktuellen Klasse oder Instanz überschrieben.</span><span class="sxs-lookup"><span data-stu-id="74c6f-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="74c6f-128">In diesem Fall die `QualifierSet_Delete` Methode setzt den Qualifizierer auf den ursprünglichen geerbten Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="74c6f-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="74c6f-129">Die Funktion gibt in diesem Fall den Statuscode `WBEM_S_RESET_TO_DEFAULT`.</span><span class="sxs-lookup"><span data-stu-id="74c6f-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="74c6f-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74c6f-130">Requirements</span></span>  
 <span data-ttu-id="74c6f-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74c6f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74c6f-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="74c6f-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="74c6f-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="74c6f-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c6f-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74c6f-134">See also</span></span>  
[<span data-ttu-id="74c6f-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="74c6f-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
