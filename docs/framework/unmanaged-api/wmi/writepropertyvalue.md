---
title: WritePropertyValue-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion WritePropertyValue schreibt Bytes in eine Eigenschaft an.
ms.date: 11/06/2017
api_name:
- WritePropertyValue
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- WritePropertyValue
helpviewer_keywords:
- WritePropertyValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a98103367f497b18f9b8fbd61a37abf9816b8356
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040403"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="f70c2-103">WritePropertyValue-Funktion</span><span class="sxs-lookup"><span data-stu-id="f70c2-103">WritePropertyValue function</span></span>
<span data-ttu-id="f70c2-104">Schreibt eine angegebene Anzahl von Bytes in eine Eigenschaft, die durch ein Eigenschaftenhandle identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="f70c2-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="f70c2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f70c2-105">Syntax</span></span>  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="f70c2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f70c2-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f70c2-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f70c2-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f70c2-108">[in] Ein Zeiger auf ein [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) Instanz.</span><span class="sxs-lookup"><span data-stu-id="f70c2-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="f70c2-109">[in] Eine ganze Zahl, die das Handle enthält, das diese Eigenschaft identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f70c2-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="f70c2-110">Das Handle abgerufen werden kann, durch den Aufruf der [GetPropertyHandle](getpropertyhandle.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="f70c2-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="f70c2-111">[in] Die Anzahl der Bytes, die auf die Eigenschaft geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f70c2-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="f70c2-112">Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="f70c2-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="f70c2-113">[out] Ein Zeiger auf das Bytearray, das Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="f70c2-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="f70c2-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f70c2-114">Return value</span></span>

<span data-ttu-id="f70c2-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="f70c2-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f70c2-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="f70c2-116">Constant</span></span>  |<span data-ttu-id="f70c2-117">Wert</span><span class="sxs-lookup"><span data-stu-id="f70c2-117">Value</span></span>  |<span data-ttu-id="f70c2-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f70c2-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f70c2-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f70c2-119">0x80041008</span></span> | <span data-ttu-id="f70c2-120">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="f70c2-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="f70c2-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="f70c2-121">0x80041005</span></span> | <span data-ttu-id="f70c2-122">Es ist ein Typenkonflikt aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f70c2-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f70c2-123">0</span><span class="sxs-lookup"><span data-stu-id="f70c2-123">0</span></span> | <span data-ttu-id="f70c2-124">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="f70c2-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f70c2-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f70c2-125">Remarks</span></span>

<span data-ttu-id="f70c2-126">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) Methode.</span><span class="sxs-lookup"><span data-stu-id="f70c2-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="f70c2-127">Mit dieser Funktion können Sie die Zeichenfolge "und" alle anderen nicht - festgelegt`DWORD` oder nicht-`QWORD` Daten.</span><span class="sxs-lookup"><span data-stu-id="f70c2-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="f70c2-128">Keine Zeichenfolge darstellen Eigenschaftswerte `lNumBytes` müssen die richtigen Datengröße des Eigenschaftentyps angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f70c2-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="f70c2-129">Für Zeichenfolgen-Eigenschaftswerten `lNumBytes` muss die Länge der angegebenen Zeichenfolge in Bytes und die Zeichenfolge selbst muss ein sogar Länge in Bytes und eine Null-Terminierungszeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="f70c2-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="f70c2-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f70c2-130">Requirements</span></span>  
<span data-ttu-id="f70c2-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f70c2-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f70c2-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f70c2-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f70c2-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f70c2-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f70c2-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f70c2-134">See also</span></span>

- [<span data-ttu-id="f70c2-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="f70c2-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
