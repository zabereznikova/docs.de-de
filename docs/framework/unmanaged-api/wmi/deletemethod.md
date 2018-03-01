---
title: DeleteMethod-Funktion (Referenz zur nicht verwalteten API)
description: "Die DeleteMethod-Funktion löscht die angegebene Methode aus der Definition einer CIM-Klasse."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 03b147d2fd76e34c6152a0b41ee14319811e9300
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="deletemethod-function"></a><span data-ttu-id="2dc3e-103">DeleteMethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="2dc3e-103">DeleteMethod function</span></span>
<span data-ttu-id="2dc3e-104">Löscht die angegebene Methode aus der Definition einer CIM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2dc3e-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="2dc3e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2dc3e-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="2dc3e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2dc3e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="2dc3e-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="2dc3e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="2dc3e-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="2dc3e-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="2dc3e-109">[in] Der Name der Methode, die aus der Tabelle zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2dc3e-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="2dc3e-110">`wszName`muss ein Zeiger auf eine gültige `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="2dc3e-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="2dc3e-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2dc3e-111">Return value</span></span>

<span data-ttu-id="2dc3e-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="2dc3e-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2dc3e-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="2dc3e-113">Constant</span></span>  |<span data-ttu-id="2dc3e-114">Wert</span><span class="sxs-lookup"><span data-stu-id="2dc3e-114">Value</span></span>  |<span data-ttu-id="2dc3e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2dc3e-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="2dc3e-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="2dc3e-116">0x80041002</span></span> | <span data-ttu-id="2dc3e-117">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2dc3e-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="2dc3e-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="2dc3e-118">0x80041006</span></span> | <span data-ttu-id="2dc3e-119">Es ist nicht genügend Arbeitsspeicher zum Abschließen des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="2dc3e-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="2dc3e-120">0</span><span class="sxs-lookup"><span data-stu-id="2dc3e-120">0</span></span> | <span data-ttu-id="2dc3e-121">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="2dc3e-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="2dc3e-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2dc3e-122">Remarks</span></span>

<span data-ttu-id="2dc3e-123">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="2dc3e-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](https://msdn.microsoft.com/library/aa391439(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="2dc3e-124">Löschen der Methode nicht unterstützt. für [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Zeiger, die auf das CIM-Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="2dc3e-124">Method deletion is not supported for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="2dc3e-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2dc3e-125">Requirements</span></span>  
 <span data-ttu-id="2dc3e-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2dc3e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dc3e-127">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2dc3e-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2dc3e-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2dc3e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dc3e-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2dc3e-129">See also</span></span>  
[<span data-ttu-id="2dc3e-130">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="2dc3e-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
