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
ms.openlocfilehash: e5a2588023309867694f344041f62be53cab9c37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590119"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="b58c3-103">WritePropertyValue-Funktion</span><span class="sxs-lookup"><span data-stu-id="b58c3-103">WritePropertyValue function</span></span>
<span data-ttu-id="b58c3-104">Schreibt eine angegebene Anzahl von Bytes in eine Eigenschaft, die durch ein Eigenschaftenhandle identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="b58c3-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b58c3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b58c3-105">Syntax</span></span>  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="b58c3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b58c3-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b58c3-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="b58c3-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b58c3-108">[in] Ein Zeiger auf ein [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) Instanz.</span><span class="sxs-lookup"><span data-stu-id="b58c3-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="b58c3-109">[in] Eine ganze Zahl, die das Handle enthält, das diese Eigenschaft identifiziert.</span><span class="sxs-lookup"><span data-stu-id="b58c3-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="b58c3-110">Das Handle abgerufen werden kann, durch den Aufruf der [GetPropertyHandle](getpropertyhandle.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="b58c3-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="b58c3-111">[in] Die Anzahl der Bytes, die auf die Eigenschaft geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="b58c3-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="b58c3-112">Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="b58c3-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="b58c3-113">[out] Ein Zeiger auf das Bytearray, das Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="b58c3-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="b58c3-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b58c3-114">Return value</span></span>

<span data-ttu-id="b58c3-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="b58c3-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b58c3-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="b58c3-116">Constant</span></span>  |<span data-ttu-id="b58c3-117">Wert</span><span class="sxs-lookup"><span data-stu-id="b58c3-117">Value</span></span>  |<span data-ttu-id="b58c3-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b58c3-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b58c3-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b58c3-119">0x80041008</span></span> | <span data-ttu-id="b58c3-120">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="b58c3-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="b58c3-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="b58c3-121">0x80041005</span></span> | <span data-ttu-id="b58c3-122">Es ist ein Typenkonflikt aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b58c3-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b58c3-123">0</span><span class="sxs-lookup"><span data-stu-id="b58c3-123">0</span></span> | <span data-ttu-id="b58c3-124">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="b58c3-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b58c3-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b58c3-125">Remarks</span></span>

<span data-ttu-id="b58c3-126">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) Methode.</span><span class="sxs-lookup"><span data-stu-id="b58c3-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="b58c3-127">Mit dieser Funktion können Sie die Zeichenfolge "und" alle anderen nicht - festgelegt`DWORD` oder nicht-`QWORD` Daten.</span><span class="sxs-lookup"><span data-stu-id="b58c3-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="b58c3-128">Keine Zeichenfolge darstellen Eigenschaftswerte `lNumBytes` müssen die richtigen Datengröße des Eigenschaftentyps angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b58c3-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="b58c3-129">Für Zeichenfolgen-Eigenschaftswerten `lNumBytes` muss die Länge der angegebenen Zeichenfolge in Bytes und die Zeichenfolge selbst muss ein sogar Länge in Bytes und eine Null-Terminierungszeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="b58c3-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="b58c3-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b58c3-130">Requirements</span></span>  
<span data-ttu-id="b58c3-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b58c3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b58c3-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b58c3-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b58c3-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b58c3-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b58c3-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b58c3-134">See also</span></span>
- [<span data-ttu-id="b58c3-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="b58c3-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
