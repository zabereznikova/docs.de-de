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
ms.openlocfilehash: 9eb96a75686a14182b9526a0832223c2b9abfc34
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136915"
---
# <a name="deletemethod-function"></a><span data-ttu-id="e405b-103">DeleteMethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="e405b-103">DeleteMethod function</span></span>
<span data-ttu-id="e405b-104">Löscht die angegebene Methode aus der Definition einer CIM-Klasse.</span><span class="sxs-lookup"><span data-stu-id="e405b-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e405b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e405b-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="e405b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e405b-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e405b-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e405b-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e405b-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="e405b-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="e405b-109">[in] Der Name der Methode, die aus der Tabelle zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e405b-109">[in] The name of the method to remove from the class table.</span></span> `wszName` <span data-ttu-id="e405b-110">muss ein Zeiger auf ein gültiges `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="e405b-110">must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="e405b-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e405b-111">Return value</span></span>

<span data-ttu-id="e405b-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="e405b-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e405b-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="e405b-113">Constant</span></span>  |<span data-ttu-id="e405b-114">Wert</span><span class="sxs-lookup"><span data-stu-id="e405b-114">Value</span></span>  |<span data-ttu-id="e405b-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e405b-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="e405b-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e405b-116">0x80041002</span></span> | <span data-ttu-id="e405b-117">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e405b-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e405b-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e405b-118">0x80041006</span></span> | <span data-ttu-id="e405b-119">Es ist nicht genügend Arbeitsspeicher zum Abschließen des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="e405b-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="e405b-120">0</span><span class="sxs-lookup"><span data-stu-id="e405b-120">0</span></span> | <span data-ttu-id="e405b-121">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="e405b-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="e405b-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e405b-122">Remarks</span></span>

<span data-ttu-id="e405b-123">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) Methode.</span><span class="sxs-lookup"><span data-stu-id="e405b-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="e405b-124">Löschen der Methode wird nicht unterstützt, für die [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Zeigern, die auf das CIM-Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="e405b-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="e405b-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e405b-125">Requirements</span></span>  
 <span data-ttu-id="e405b-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e405b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e405b-127">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e405b-127">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="e405b-128">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e405b-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e405b-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e405b-129">See also</span></span>

- [<span data-ttu-id="e405b-130">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="e405b-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
