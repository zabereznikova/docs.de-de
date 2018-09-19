---
title: DeleteMethod-Funktion (Referenz zur nicht verwalteten API)
description: DeleteMethod-Funktion löscht die angegebene Methode aus der Definition einer CIM-Klasse.
ms.date: 11/06/2017
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
ms.openlocfilehash: 5996ce41c80cb54c4fcb9104c2993c85bcc2b466
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46323573"
---
# <a name="deletemethod-function"></a><span data-ttu-id="4cec1-103">DeleteMethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="4cec1-103">DeleteMethod function</span></span>
<span data-ttu-id="4cec1-104">Löscht die angegebene Methode aus der Definition einer CIM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="4cec1-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="4cec1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4cec1-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="4cec1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4cec1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4cec1-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cec1-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4cec1-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="4cec1-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="4cec1-109">[in] Der Name der Methode, die aus der Tabelle zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="4cec1-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="4cec1-110">`wszName` muss ein Zeiger auf ein gültiges `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="4cec1-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="4cec1-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4cec1-111">Return value</span></span>

<span data-ttu-id="4cec1-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="4cec1-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4cec1-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="4cec1-113">Constant</span></span>  |<span data-ttu-id="4cec1-114">Wert</span><span class="sxs-lookup"><span data-stu-id="4cec1-114">Value</span></span>  |<span data-ttu-id="4cec1-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4cec1-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="4cec1-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="4cec1-116">0x80041002</span></span> | <span data-ttu-id="4cec1-117">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4cec1-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4cec1-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4cec1-118">0x80041006</span></span> | <span data-ttu-id="4cec1-119">Es ist nicht genügend Arbeitsspeicher zum Abschließen des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="4cec1-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="4cec1-120">0</span><span class="sxs-lookup"><span data-stu-id="4cec1-120">0</span></span> | <span data-ttu-id="4cec1-121">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="4cec1-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="4cec1-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4cec1-122">Remarks</span></span>

<span data-ttu-id="4cec1-123">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) Methode.</span><span class="sxs-lookup"><span data-stu-id="4cec1-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="4cec1-124">Löschen der Methode wird nicht unterstützt, für die [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Zeigern, die auf das CIM-Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="4cec1-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="4cec1-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4cec1-125">Requirements</span></span>  
 <span data-ttu-id="4cec1-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cec1-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cec1-127">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4cec1-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4cec1-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4cec1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cec1-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cec1-129">See also</span></span>  
[<span data-ttu-id="4cec1-130">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="4cec1-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
