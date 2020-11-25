---
title: DeleteMethod-Funktion (Referenz zur nicht verwalteten API)
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
ms.openlocfilehash: 8ca58ed3510360b20577890055e4284869d1bf94
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708100"
---
# <a name="deletemethod-function"></a><span data-ttu-id="9ddc3-103">DeleteMethod-Funktion</span><span class="sxs-lookup"><span data-stu-id="9ddc3-103">DeleteMethod function</span></span>

<span data-ttu-id="9ddc3-104">Löscht die angegebene Methode aus einer CIM-Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="9ddc3-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="9ddc3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ddc3-105">Syntax</span></span>  
  
```cpp  
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="9ddc3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9ddc3-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="9ddc3-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ddc3-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="9ddc3-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="9ddc3-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="9ddc3-109">in Der Name der Methode, die aus der Klassen Tabelle entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ddc3-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="9ddc3-110">`wszName` muss ein Zeiger auf einen gültigen sein `LPCWSTR` .</span><span class="sxs-lookup"><span data-stu-id="9ddc3-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="9ddc3-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9ddc3-111">Return value</span></span>

<span data-ttu-id="9ddc3-112">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="9ddc3-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9ddc3-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="9ddc3-113">Constant</span></span>  |<span data-ttu-id="9ddc3-114">Wert</span><span class="sxs-lookup"><span data-stu-id="9ddc3-114">Value</span></span>  |<span data-ttu-id="9ddc3-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9ddc3-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="9ddc3-116">0x80041002 angezeigt</span><span class="sxs-lookup"><span data-stu-id="9ddc3-116">0x80041002</span></span> | <span data-ttu-id="9ddc3-117">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="9ddc3-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="9ddc3-118">0x80041006</span><span class="sxs-lookup"><span data-stu-id="9ddc3-118">0x80041006</span></span> | <span data-ttu-id="9ddc3-119">Es steht nicht genügend Arbeitsspeicher zur Verfügung, um den Vorgang durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="9ddc3-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="9ddc3-120">0</span><span class="sxs-lookup"><span data-stu-id="9ddc3-120">0</span></span> | <span data-ttu-id="9ddc3-121">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="9ddc3-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="9ddc3-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9ddc3-122">Remarks</span></span>

<span data-ttu-id="9ddc3-123">Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject::D eletemethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) -Methode.</span><span class="sxs-lookup"><span data-stu-id="9ddc3-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="9ddc3-124">Das Löschen von Methoden wird für [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Zeiger, die auf CIM-Instanzen verweisen, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9ddc3-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="9ddc3-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9ddc3-125">Requirements</span></span>  

 <span data-ttu-id="9ddc3-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ddc3-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ddc3-127">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="9ddc3-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9ddc3-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9ddc3-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ddc3-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9ddc3-129">See also</span></span>

- [<span data-ttu-id="9ddc3-130">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="9ddc3-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
