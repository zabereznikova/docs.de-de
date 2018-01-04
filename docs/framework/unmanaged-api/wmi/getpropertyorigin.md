---
title: GetPropertyOrigin-Funktion (Unmnaged-API-Referenz)
description: Die Funktion GetPropertyOrigin bestimmt die Klasse, die in der eine Eigenschaft deklariert wird.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyOrigin
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyOrigin
helpviewer_keywords: GetPropertyOrigin function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0a79bfc62ad776cb2bfab2c143d19761d64358bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="d7a73-103">GetPropertyOrigin-Funktion</span><span class="sxs-lookup"><span data-stu-id="d7a73-103">GetPropertyOrigin function</span></span>
<span data-ttu-id="d7a73-104">Bestimmt die Klasse, die in der eine Eigenschaft deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="d7a73-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="d7a73-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7a73-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="d7a73-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7a73-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d7a73-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d7a73-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d7a73-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="d7a73-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="d7a73-109">[in] Der Name der Eigenschaft für das Objekt, dessen besitzende Klasse angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="d7a73-109">[in] The name of the property for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="d7a73-110">[out] Erhält den Namen der Klasse, die die Eigenschaft gehört.</span><span class="sxs-lookup"><span data-stu-id="d7a73-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="d7a73-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d7a73-111">Return value</span></span>

<span data-ttu-id="d7a73-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="d7a73-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d7a73-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="d7a73-113">Constant</span></span>  |<span data-ttu-id="d7a73-114">Wert</span><span class="sxs-lookup"><span data-stu-id="d7a73-114">Value</span></span>  |<span data-ttu-id="d7a73-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d7a73-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="d7a73-116">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="d7a73-116">0x80041001</span></span> | <span data-ttu-id="d7a73-117">Ein allgemeiner Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d7a73-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="d7a73-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="d7a73-118">0x80041002</span></span> | <span data-ttu-id="d7a73-119">Die angegebene Eigenschaft wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="d7a73-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d7a73-120">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="d7a73-120">0x80041008</span></span> | <span data-ttu-id="d7a73-121">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="d7a73-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d7a73-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d7a73-122">0x80041006</span></span> | <span data-ttu-id="d7a73-123">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d7a73-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d7a73-124">0</span><span class="sxs-lookup"><span data-stu-id="d7a73-124">0</span></span> | <span data-ttu-id="d7a73-125">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d7a73-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d7a73-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7a73-126">Remarks</span></span>

<span data-ttu-id="d7a73-127">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="d7a73-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="d7a73-128">Da eine Klasse Eigenschaften aus einem oder mehreren Basisklassen erben kann, möchten Entwickler häufig die Eigenschaft zu bestimmen, in der eine bestimmte Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d7a73-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="d7a73-129">Die `pstrClassName` Parameter muss nicht auf eine gültige zeigen `BSTR` , bevor die Funktion aufgerufen wird, da dies ist ein `out` Parameter; diese Zeiger wird aufgehoben, wenn die Funktion zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="d7a73-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="d7a73-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7a73-130">Requirements</span></span>  
<span data-ttu-id="d7a73-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7a73-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7a73-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d7a73-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d7a73-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d7a73-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7a73-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7a73-134">See also</span></span>  
[<span data-ttu-id="d7a73-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="d7a73-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
