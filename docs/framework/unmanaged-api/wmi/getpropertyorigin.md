---
title: GetPropertyOrigin-Funktion (Unmnaged-API-Referenz)
description: GetPropertyOrigin-Funktion bestimmt die Klasse, die in der eine Eigenschaft deklariert ist.
ms.date: 11/06/2017
api_name:
- GetPropertyOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyOrigin
helpviewer_keywords:
- GetPropertyOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86c512f25c40f201d818b6789c6410bfb095b878
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933516"
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="07922-103">GetPropertyOrigin-Funktion</span><span class="sxs-lookup"><span data-stu-id="07922-103">GetPropertyOrigin function</span></span>
<span data-ttu-id="07922-104">Bestimmt die Klasse, die in der eine Eigenschaft deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="07922-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="07922-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="07922-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="07922-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="07922-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="07922-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="07922-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="07922-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="07922-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="07922-109">[in] Der Name der Eigenschaft für das Objekt, dessen übergeordnete Klasse angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="07922-109">[in] The name of the property for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="07922-110">[out] Erhält den Namen der Klasse, die die Eigenschaft besitzt.</span><span class="sxs-lookup"><span data-stu-id="07922-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="07922-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="07922-111">Return value</span></span>

<span data-ttu-id="07922-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="07922-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="07922-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="07922-113">Constant</span></span>  |<span data-ttu-id="07922-114">Wert</span><span class="sxs-lookup"><span data-stu-id="07922-114">Value</span></span>  |<span data-ttu-id="07922-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07922-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="07922-116">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="07922-116">0x80041001</span></span> | <span data-ttu-id="07922-117">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="07922-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="07922-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="07922-118">0x80041002</span></span> | <span data-ttu-id="07922-119">Die angegebene Eigenschaft wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="07922-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="07922-120">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="07922-120">0x80041008</span></span> | <span data-ttu-id="07922-121">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="07922-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="07922-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="07922-122">0x80041006</span></span> | <span data-ttu-id="07922-123">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="07922-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="07922-124">0</span><span class="sxs-lookup"><span data-stu-id="07922-124">0</span></span> | <span data-ttu-id="07922-125">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="07922-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="07922-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07922-126">Remarks</span></span>

<span data-ttu-id="07922-127">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) Methode.</span><span class="sxs-lookup"><span data-stu-id="07922-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) method.</span></span>

<span data-ttu-id="07922-128">Da eine Klasse Eigenschaften aus einem oder mehreren Basisklassen erben kann, möchten Entwickler häufig bestimmen Sie die Eigenschaft in der eine bestimmte Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="07922-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="07922-129">Die `pstrClassName` Parameter muss nicht auf einen gültigen zeigen `BSTR` , bevor die Funktion aufgerufen wird, da es sich handelt ein `out` Parameter; diese Zeiger wird nicht aufgehoben werden, nachdem die Funktion.</span><span class="sxs-lookup"><span data-stu-id="07922-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="07922-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="07922-130">Requirements</span></span>  
<span data-ttu-id="07922-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07922-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07922-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="07922-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="07922-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="07922-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07922-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07922-134">See also</span></span>  
[<span data-ttu-id="07922-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="07922-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
