---
title: WritePropertyValue-Funktion (Nicht verwaltete API-Referenz)
description: Die WritePropertyValue-Funktion schreibt Bytes in eine Eigenschaft.
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
ms.openlocfilehash: 4a950beef2e9bf8c0230d6a38008d75f89373410
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174835"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="34138-103">WritePropertyValue-Funktion</span><span class="sxs-lookup"><span data-stu-id="34138-103">WritePropertyValue function</span></span>
<span data-ttu-id="34138-104">Schreibt eine angegebene Anzahl von Bytes in eine Eigenschaft, die durch ein Eigenschaftenhandle identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="34138-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="34138-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="34138-105">Syntax</span></span>  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
);
```  

## <a name="parameters"></a><span data-ttu-id="34138-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="34138-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="34138-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="34138-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="34138-108">[in] Ein Zeiger auf eine [IWbemObjectAccess-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)</span><span class="sxs-lookup"><span data-stu-id="34138-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="34138-109">[in] Eine ganze Zahl, die das Handle enthält, das diese Eigenschaft identifiziert.</span><span class="sxs-lookup"><span data-stu-id="34138-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="34138-110">Das Handle kann abgerufen werden, indem die [GetPropertyHandle-Funktion](getpropertyhandle.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="34138-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>

`lNumBytes`  
<span data-ttu-id="34138-111">[in] Die Anzahl der Bytes, die in die Eigenschaft geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="34138-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="34138-112">Weitere Informationen finden Sie im Abschnitt ["Bemerkungen".](#remarks)</span><span class="sxs-lookup"><span data-stu-id="34138-112">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="34138-113">`pHandle`[out] Ein Zeiger auf das Bytearray, das die Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="34138-113">`pHandle` [out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="34138-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="34138-114">Return value</span></span>

<span data-ttu-id="34138-115">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="34138-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="34138-116">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="34138-116">Constant</span></span>  |<span data-ttu-id="34138-117">value</span><span class="sxs-lookup"><span data-stu-id="34138-117">Value</span></span>  |<span data-ttu-id="34138-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34138-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="34138-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="34138-119">0x80041008</span></span> | <span data-ttu-id="34138-120">Ein Parameter ist nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="34138-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="34138-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="34138-121">0x80041005</span></span> | <span data-ttu-id="34138-122">Es ist ein Typenkonflikt aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="34138-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="34138-123">0</span><span class="sxs-lookup"><span data-stu-id="34138-123">0</span></span> | <span data-ttu-id="34138-124">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="34138-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="34138-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="34138-125">Remarks</span></span>

<span data-ttu-id="34138-126">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::WritePropertyValue-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue)</span><span class="sxs-lookup"><span data-stu-id="34138-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="34138-127">Verwenden Sie diese Funktion, um`DWORD` Zeichenfolgen`QWORD` und alle anderen Nicht- oder Nicht-Daten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="34138-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="34138-128">Bei Nicht-Zeichenfolgen-Eigenschaftswerten `lNumBytes` muss die richtige Datengröße des angegebenen Eigenschaftstyps angegeben sein.</span><span class="sxs-lookup"><span data-stu-id="34138-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="34138-129">Für Zeichenfolgeneigenschaftswerte `lNumBytes` muss die Länge der angegebenen Zeichenfolge in Bytes sein, und die Zeichenfolge selbst muss eine gerade Länge in Bytes haben und mit einem Null-Beendigungszeichen gefolgt werden.</span><span class="sxs-lookup"><span data-stu-id="34138-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="34138-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="34138-130">Requirements</span></span>  
<span data-ttu-id="34138-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34138-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34138-132">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="34138-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="34138-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="34138-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34138-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34138-134">See also</span></span>

- [<span data-ttu-id="34138-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="34138-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
