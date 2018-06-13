---
title: GetQualifierSet-Funktion (Referenz zur nicht verwalteten API)
description: Die GetQualifierSet-Funktion ruft den Qualifizierer für eine Klasse oder Instanz festlegen.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b50befa4346e17048598afd3d018dbde2fe8572
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458561"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="70f01-103">GetQualifierSet-Funktion</span><span class="sxs-lookup"><span data-stu-id="70f01-103">GetQualifierSet function</span></span>
<span data-ttu-id="70f01-104">Ruft den Qualifizierer für die Instanz einer Klasse oder einer Klassendefinition festgelegt.</span><span class="sxs-lookup"><span data-stu-id="70f01-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="70f01-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="70f01-105">Syntax</span></span>  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="70f01-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="70f01-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="70f01-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="70f01-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="70f01-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="70f01-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="70f01-109">[out] Empfängt den Schnittstellenzeiger, der Zugriff auf die Qualifizierer des Klassenobjekts ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="70f01-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="70f01-110">`ppQualSet` darf nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="70f01-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="70f01-111">Wenn ein Fehler auftritt, ein neues Objekt nicht zurückgegeben wird und der Zeiger bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="70f01-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="70f01-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="70f01-112">Return value</span></span>

<span data-ttu-id="70f01-113">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="70f01-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="70f01-114">Konstante</span><span class="sxs-lookup"><span data-stu-id="70f01-114">Constant</span></span>  |<span data-ttu-id="70f01-115">Wert</span><span class="sxs-lookup"><span data-stu-id="70f01-115">Value</span></span>  |<span data-ttu-id="70f01-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70f01-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="70f01-117">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="70f01-117">0x80041001</span></span> | <span data-ttu-id="70f01-118">Ein allgemeiner Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="70f01-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="70f01-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="70f01-119">0x80041002</span></span> | <span data-ttu-id="70f01-120">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="70f01-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="70f01-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="70f01-121">0x80041006</span></span> | <span data-ttu-id="70f01-122">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="70f01-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="70f01-123">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="70f01-123">0x80041008</span></span> | <span data-ttu-id="70f01-124">Ein Parameter ist `null`.</span><span class="sxs-lookup"><span data-stu-id="70f01-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="70f01-125">0</span><span class="sxs-lookup"><span data-stu-id="70f01-125">0</span></span> | <span data-ttu-id="70f01-126">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="70f01-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="70f01-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70f01-127">Remarks</span></span>

<span data-ttu-id="70f01-128">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::GetQualifierSet](https://msdn.microsoft.com/library/aa391451(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="70f01-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](https://msdn.microsoft.com/library/aa391451(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="70f01-129">Die [IWbemQualifierSet Zeiger](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) ermöglicht den Aufrufer hinzufügen, bearbeiten oder löschen diese Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="70f01-129">The [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="70f01-130">Solche Qualifizierer hinzugefügt, bearbeitet oder gelöscht, gelten für die gesamte Instanz oder Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="70f01-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="70f01-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="70f01-131">Requirements</span></span>  
<span data-ttu-id="70f01-132">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70f01-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70f01-133">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="70f01-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="70f01-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="70f01-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f01-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70f01-135">See also</span></span>  
[<span data-ttu-id="70f01-136">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="70f01-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
