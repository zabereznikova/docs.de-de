---
title: Klon Funktion (Referenz zur nicht verwalteten API)
description: Die Clone-Funktion gibt ein neues-Objekt zurück, das ein kompletter Klon der aktuellen ist.
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c8e7781a3efe7679ef2e05747862911db88bcc5f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141614"
---
# <a name="clone-function"></a><span data-ttu-id="2fdc3-103">Clone-Funktion</span><span class="sxs-lookup"><span data-stu-id="2fdc3-103">Clone function</span></span>
<span data-ttu-id="2fdc3-104">Gibt ein neues Objekt zurück, das ein vollständiger Klon des aktuellen Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="2fdc3-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2fdc3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fdc3-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="2fdc3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fdc3-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="2fdc3-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fdc3-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="2fdc3-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="2fdc3-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="2fdc3-109">vorgenommen Ein neues-Objekt, das eine komplette `ptr`ist.</span><span class="sxs-lookup"><span data-stu-id="2fdc3-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="2fdc3-110">Dieses Argument kann nicht `null` werden, wenn es die Kopie des aktuellen-Objekts empfängt.</span><span class="sxs-lookup"><span data-stu-id="2fdc3-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="2fdc3-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2fdc3-111">Return value</span></span>

<span data-ttu-id="2fdc3-112">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="2fdc3-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2fdc3-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="2fdc3-113">Constant</span></span>  |<span data-ttu-id="2fdc3-114">Wert</span><span class="sxs-lookup"><span data-stu-id="2fdc3-114">Value</span></span>  |<span data-ttu-id="2fdc3-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fdc3-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="2fdc3-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="2fdc3-116">0x80041001</span></span> | <span data-ttu-id="2fdc3-117">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2fdc3-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="2fdc3-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="2fdc3-118">0x80041008</span></span> | <span data-ttu-id="2fdc3-119">`null` wurde als Parameter angegeben und ist in dieser Verwendung nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="2fdc3-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="2fdc3-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="2fdc3-120">0x80041006</span></span> | <span data-ttu-id="2fdc3-121">Es ist nicht genügend Arbeitsspeicher verfügbar, um das Objekt zu klonen.</span><span class="sxs-lookup"><span data-stu-id="2fdc3-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="2fdc3-122">0</span><span class="sxs-lookup"><span data-stu-id="2fdc3-122">0</span></span> | <span data-ttu-id="2fdc3-123">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="2fdc3-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="2fdc3-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2fdc3-124">Remarks</span></span>

<span data-ttu-id="2fdc3-125">Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) -Methode.</span><span class="sxs-lookup"><span data-stu-id="2fdc3-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="2fdc3-126">Das geklonte Objekt ist ein COM-Objekt mit einem Verweis Zähler von 1.</span><span class="sxs-lookup"><span data-stu-id="2fdc3-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="2fdc3-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2fdc3-127">Requirements</span></span>  
 <span data-ttu-id="2fdc3-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fdc3-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fdc3-129">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="2fdc3-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2fdc3-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2fdc3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fdc3-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fdc3-131">See also</span></span>

- [<span data-ttu-id="2fdc3-132">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="2fdc3-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
