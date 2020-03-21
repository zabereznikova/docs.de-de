---
title: DeleteMethod-Funktion (Nicht verwaltete API-Referenz)
description: Die DeleteMethod-Funktion löscht die angegebene Methode aus einer CIM-Klassendefinition.
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
ms.openlocfilehash: 4059555d74c0b0f151332ddcf9faedecf238e795
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174991"
---
# <a name="deletemethod-function"></a><span data-ttu-id="e7298-103">DeleteMethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="e7298-103">DeleteMethod function</span></span>
<span data-ttu-id="e7298-104">Löscht die angegebene Methode aus einer CIM-Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="e7298-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e7298-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7298-105">Syntax</span></span>  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="e7298-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7298-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e7298-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e7298-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e7298-108">[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="e7298-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="e7298-109">[in] Der Name der Methode, die aus der Klassentabelle entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7298-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="e7298-110">`wszName`muss ein Zeiger auf `LPCWSTR`eine gültige sein.</span><span class="sxs-lookup"><span data-stu-id="e7298-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="e7298-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e7298-111">Return value</span></span>

<span data-ttu-id="e7298-112">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="e7298-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e7298-113">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="e7298-113">Constant</span></span>  |<span data-ttu-id="e7298-114">value</span><span class="sxs-lookup"><span data-stu-id="e7298-114">Value</span></span>  |<span data-ttu-id="e7298-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7298-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="e7298-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e7298-116">0x80041002</span></span> | <span data-ttu-id="e7298-117">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e7298-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e7298-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e7298-118">0x80041006</span></span> | <span data-ttu-id="e7298-119">Es steht nicht genügend Arbeitsspeicher zur Verfügung, um den Vorgang durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="e7298-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="e7298-120">0</span><span class="sxs-lookup"><span data-stu-id="e7298-120">0</span></span> | <span data-ttu-id="e7298-121">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="e7298-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="e7298-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e7298-122">Remarks</span></span>

<span data-ttu-id="e7298-123">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::DeleteMethod-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod)</span><span class="sxs-lookup"><span data-stu-id="e7298-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="e7298-124">Das Löschen von Methoden wird für [IWbemClassObject-Zeiger, die](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) auf CIM-Instanzen verweisen, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e7298-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="e7298-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e7298-125">Requirements</span></span>  
 <span data-ttu-id="e7298-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7298-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7298-127">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e7298-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e7298-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e7298-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7298-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7298-129">See also</span></span>

- [<span data-ttu-id="e7298-130">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="e7298-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
