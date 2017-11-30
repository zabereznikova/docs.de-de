---
title: WritePropertyValue-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion WritePropertyValue schreibt Bytes auf eine Eigenschaft an.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: WritePropertyValue
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: WritePropertyValue
helpviewer_keywords: WritePropertyValue function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26337a13ab9840b79c253d4af2d84a10e70877c5
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="2ab27-103">WritePropertyValue-Funktion</span><span class="sxs-lookup"><span data-stu-id="2ab27-103">WritePropertyValue function</span></span>
<span data-ttu-id="2ab27-104">Schreibt eine angegebene Anzahl von Bytes an eine Eigenschaft, die durch ein Eigenschaftshandle identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2ab27-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="2ab27-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ab27-105">Syntax</span></span>  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="2ab27-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ab27-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="2ab27-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ab27-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="2ab27-108">[in] Ein Zeiger auf ein [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="2ab27-108">[in] A pointer to an [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span></span>

`lHandle`  
<span data-ttu-id="2ab27-109">[in] Eine ganze Zahl, die das Handle enthält, das diese Eigenschaft kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="2ab27-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="2ab27-110">Das Handle abgerufen werden kann, durch Aufrufen der [GetPropertyHandle](getpropertyhandle.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="2ab27-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="2ab27-111">[in] Die Anzahl der Bytes, die der Eigenschaft geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="2ab27-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="2ab27-112">Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="2ab27-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="2ab27-113">[out] Ein Zeiger auf das Bytearray, das Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="2ab27-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="2ab27-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2ab27-114">Return value</span></span>

<span data-ttu-id="2ab27-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="2ab27-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2ab27-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="2ab27-116">Constant</span></span>  |<span data-ttu-id="2ab27-117">Wert</span><span class="sxs-lookup"><span data-stu-id="2ab27-117">Value</span></span>  |<span data-ttu-id="2ab27-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ab27-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="2ab27-119">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="2ab27-119">0x80041008</span></span> | <span data-ttu-id="2ab27-120">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="2ab27-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="2ab27-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="2ab27-121">0x80041005</span></span> | <span data-ttu-id="2ab27-122">Ein Typenkonflikt aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="2ab27-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="2ab27-123">0</span><span class="sxs-lookup"><span data-stu-id="2ab27-123">0</span></span> | <span data-ttu-id="2ab27-124">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="2ab27-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="2ab27-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ab27-125">Remarks</span></span>

<span data-ttu-id="2ab27-126">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="2ab27-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="2ab27-127">Mit dieser Funktion können Sie die Zeichenfolge "und" alle anderen nicht - festgelegt`DWORD` oder nicht-`QWORD` Daten.</span><span class="sxs-lookup"><span data-stu-id="2ab27-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="2ab27-128">Für Eigenschaftswerte Objektressourcen `lNumBytes` müssen die richtigen Datengröße des Eigenschaftentyps angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2ab27-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="2ab27-129">Für Zeichenfolge-Eigenschaftswerte `lNumBytes` muss die Länge der angegebenen Zeichenfolge in Bytes und die Zeichenfolge selbst muss eine Länge in Bytes, und mit einem Null-Abschlusszeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="2ab27-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="2ab27-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ab27-130">Requirements</span></span>  
<span data-ttu-id="2ab27-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ab27-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ab27-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2ab27-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2ab27-133">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2ab27-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab27-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ab27-134">See also</span></span>  
[<span data-ttu-id="2ab27-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="2ab27-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
