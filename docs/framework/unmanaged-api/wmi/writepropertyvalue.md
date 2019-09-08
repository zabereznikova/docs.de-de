---
title: Funktion "Beschreib tepropertyvalue" (Referenz zur nicht verwalteten API)
description: Die Funktion "schreitepropertyvalue" schreibt Bytes in eine Eigenschaft.
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
ms.openlocfilehash: a3c42129835f9b30bed493a0992d49d7e2a458e2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798181"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="195f9-103">Funktion "schreitepropertyvalue"</span><span class="sxs-lookup"><span data-stu-id="195f9-103">WritePropertyValue function</span></span>
<span data-ttu-id="195f9-104">Schreibt eine angegebene Anzahl von Bytes in eine Eigenschaft, die durch ein Eigenschaftenhandle identifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="195f9-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="195f9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="195f9-105">Syntax</span></span>  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="195f9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="195f9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="195f9-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="195f9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="195f9-108">in Ein Zeiger auf eine [iwbemubjectaccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="195f9-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="195f9-109">in Eine ganze Zahl, die das Handle enthält, das diese Eigenschaft identifiziert.</span><span class="sxs-lookup"><span data-stu-id="195f9-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="195f9-110">Das Handle kann durch Aufrufen der [getpropertyhandle](getpropertyhandle.md) -Funktion abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="195f9-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="195f9-111">in Die Anzahl der Bytes, die in die Eigenschaft geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="195f9-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="195f9-112">Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="195f9-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="195f9-113">vorgenommen Ein Zeiger auf das Bytearray, das die Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="195f9-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="195f9-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="195f9-114">Return value</span></span>

<span data-ttu-id="195f9-115">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="195f9-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="195f9-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="195f9-116">Constant</span></span>  |<span data-ttu-id="195f9-117">Wert</span><span class="sxs-lookup"><span data-stu-id="195f9-117">Value</span></span>  |<span data-ttu-id="195f9-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="195f9-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="195f9-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="195f9-119">0x80041008</span></span> | <span data-ttu-id="195f9-120">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="195f9-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="195f9-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="195f9-121">0x80041005</span></span> | <span data-ttu-id="195f9-122">Es ist ein Typen Konflikt aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="195f9-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="195f9-123">0</span><span class="sxs-lookup"><span data-stu-id="195f9-123">0</span></span> | <span data-ttu-id="195f9-124">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="195f9-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="195f9-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="195f9-125">Remarks</span></span>

<span data-ttu-id="195f9-126">Diese Funktion umschließt einen aufzurufenden Befehl an die [IWbemClassObject:: Write-PropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) -Methode.</span><span class="sxs-lookup"><span data-stu-id="195f9-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="195f9-127">Verwenden Sie diese Funktion, um die Zeichenfolge und alle`DWORD` anderen nicht-`QWORD` oder nicht-Daten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="195f9-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="195f9-128">Für nicht-Zeichen folgen- `lNumBytes` Eigenschaftswerte muss die richtige Datengröße des angegebenen Eigenschaftentyps sein.</span><span class="sxs-lookup"><span data-stu-id="195f9-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="195f9-129">Für Zeichen folgen Eigenschafts `lNumBytes` Werte muss die Länge der angegebenen Zeichenfolge in Bytes sein, und die Zeichenfolge selbst muss eine gerade Länge in Bytes aufweisen und mit einem NULL-Terminierungs Zeichen befolgt werden.</span><span class="sxs-lookup"><span data-stu-id="195f9-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="195f9-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="195f9-130">Requirements</span></span>  
<span data-ttu-id="195f9-131">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="195f9-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="195f9-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="195f9-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="195f9-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="195f9-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195f9-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="195f9-134">See also</span></span>

- [<span data-ttu-id="195f9-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="195f9-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
