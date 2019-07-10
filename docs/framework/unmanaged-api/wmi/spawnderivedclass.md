---
title: SpawnDerivedClass-Funktion (Referenz zur nicht verwalteten API)
description: Die SpawnDerivedClass-Funktion erstellt ein neues Objekt, das von einem Objekt abgeleitet ist.
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f05f349699b28262c1628cadc6e9a0fb0a3459c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783104"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="6ce98-103">SpawnDerivedClass-Funktion</span><span class="sxs-lookup"><span data-stu-id="6ce98-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="6ce98-104">Erstellt ein neu abgeleitetes Klassenobjekt aus einem angegebenen Objekt.</span><span class="sxs-lookup"><span data-stu-id="6ce98-104">Creates a newly derived class object from a specified object.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6ce98-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ce98-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a><span data-ttu-id="6ce98-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6ce98-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="6ce98-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="6ce98-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="6ce98-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="6ce98-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="6ce98-109">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="6ce98-109">[in] Reserved.</span></span> <span data-ttu-id="6ce98-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="6ce98-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="6ce98-111">[out] Erhält der Zeiger auf das neue Objekt der Klasse-Definition.</span><span class="sxs-lookup"><span data-stu-id="6ce98-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="6ce98-112">Wenn ein Fehler auftritt, ist ein neues Objekt nicht zurückgegeben, und `ppNewClass` wird links unverändert.</span><span class="sxs-lookup"><span data-stu-id="6ce98-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="6ce98-113">Der Wert darf nicht sein `null`.</span><span class="sxs-lookup"><span data-stu-id="6ce98-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="6ce98-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6ce98-114">Return value</span></span>

<span data-ttu-id="6ce98-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="6ce98-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6ce98-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="6ce98-116">Constant</span></span>  |<span data-ttu-id="6ce98-117">Wert</span><span class="sxs-lookup"><span data-stu-id="6ce98-117">Value</span></span>  |<span data-ttu-id="6ce98-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ce98-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="6ce98-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="6ce98-119">0x80041001</span></span> | <span data-ttu-id="6ce98-120">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="6ce98-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="6ce98-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="6ce98-121">0x80041016</span></span> | <span data-ttu-id="6ce98-122">Es wurde eine ungültige Operation, z. B. das Erzeugen einer Klasse von einer Instanz angefordert.</span><span class="sxs-lookup"><span data-stu-id="6ce98-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="6ce98-123">Die Quellklasse wurde nicht vollständig definiert oder mit Windows-Verwaltung, registriert werden, damit eine neue abgeleitete Klasse nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="6ce98-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6ce98-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6ce98-124">0x80041006</span></span> | <span data-ttu-id="6ce98-125">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6ce98-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6ce98-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6ce98-126">0x80041008</span></span> | <span data-ttu-id="6ce98-127">`ppNewClass` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="6ce98-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="6ce98-128">0</span><span class="sxs-lookup"><span data-stu-id="6ce98-128">0</span></span> | <span data-ttu-id="6ce98-129">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="6ce98-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="6ce98-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ce98-130">Remarks</span></span>

<span data-ttu-id="6ce98-131">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) Methode.</span><span class="sxs-lookup"><span data-stu-id="6ce98-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="6ce98-132">`ptr` muss eine Definition einer Klasse, die die übergeordnete Klasse des Objekts erzeugten wird.</span><span class="sxs-lookup"><span data-stu-id="6ce98-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="6ce98-133">Das zurückgegebene Objekt ist eine Unterklasse des aktuellen Objekts.</span><span class="sxs-lookup"><span data-stu-id="6ce98-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="6ce98-134">Das neue Objekt im zurückgegebenen `ppNewClass` wird automatisch eine Unterklasse des aktuellen Objekts.</span><span class="sxs-lookup"><span data-stu-id="6ce98-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="6ce98-135">Dieses Verhalten kann nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6ce98-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="6ce98-136">Es gibt keine andere Methode, die von der Unterklasse (abgeleitete Klassen) erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="6ce98-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="6ce98-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6ce98-137">Requirements</span></span>  
 <span data-ttu-id="6ce98-138">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ce98-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ce98-139">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6ce98-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6ce98-140">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6ce98-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ce98-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ce98-141">See also</span></span>

- [<span data-ttu-id="6ce98-142">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="6ce98-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
