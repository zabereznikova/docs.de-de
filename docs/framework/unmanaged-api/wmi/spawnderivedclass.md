---
title: SpawnDerivedClass-Funktion (Referenz zur nicht verwalteten API)
description: Die SpawnDerivedClass-Funktion erstellt ein neues Objekt, das von einem Objekt abgeleitet wird.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SpawnDerivedClass
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SpawnDerivedClass
helpviewer_keywords: SpawnDerivedClass function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51a0dd0013b1bb3898bcc81ee2d64be20a5b6ecc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="0e4a9-103">SpawnDerivedClass-Funktion</span><span class="sxs-lookup"><span data-stu-id="0e4a9-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="0e4a9-104">Erstellt ein Klassenobjekt für die neu abgeleitete aus einem angegebenen Objekt.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-104">Creates a newly derived class object from a specified object.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0e4a9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e4a9-105">Syntax</span></span>  
  
```  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a><span data-ttu-id="0e4a9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0e4a9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0e4a9-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0e4a9-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="0e4a9-109">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-109">[in] Reserved.</span></span> <span data-ttu-id="0e4a9-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="0e4a9-111">[out] Erhält den Zeiger auf das neue Objekt der Klasse Definition an.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="0e4a9-112">Wenn ein Fehler auftritt, wird ein neues Objekt nicht zurückgegeben, und `ppNewClass` ist der linke unverändert bleiben sollen.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="0e4a9-113">Der Wert darf nicht sein `null`.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="0e4a9-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0e4a9-114">Return value</span></span>

<span data-ttu-id="0e4a9-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="0e4a9-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0e4a9-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="0e4a9-116">Constant</span></span>  |<span data-ttu-id="0e4a9-117">Wert</span><span class="sxs-lookup"><span data-stu-id="0e4a9-117">Value</span></span>  |<span data-ttu-id="0e4a9-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e4a9-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="0e4a9-119">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="0e4a9-119">0x80041001</span></span> | <span data-ttu-id="0e4a9-120">Ein allgemeiner Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="0e4a9-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="0e4a9-121">0x80041016</span></span> | <span data-ttu-id="0e4a9-122">Es wurde eine ungültige Operation, z. B. Erstellen einer Klasse aus einer Instanz angefordert.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="0e4a9-123">Die Quellklasse wurde nicht vollständig definiert oder bei der Verwaltung von Windows registriert werden, damit eine neue abgeleitete Klasse nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0e4a9-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0e4a9-124">0x80041006</span></span> | <span data-ttu-id="0e4a9-125">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0e4a9-126">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="0e4a9-126">0x80041008</span></span> | <span data-ttu-id="0e4a9-127">`ppNewClass` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0e4a9-128">0</span><span class="sxs-lookup"><span data-stu-id="0e4a9-128">0</span></span> | <span data-ttu-id="0e4a9-129">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0e4a9-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e4a9-130">Remarks</span></span>

<span data-ttu-id="0e4a9-131">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="0e4a9-132">`ptr`muss eine Definition einer Klasse, die die übergeordnete Klasse des Objekts erzeugten wird.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="0e4a9-133">Das zurückgegebene Objekt ist eine Unterklasse des aktuellen Objekts.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="0e4a9-134">Das neue Objekt im zurückgegebenen `ppNewClass` wird automatisch eine Unterklasse des aktuellen Objekts.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="0e4a9-135">Dieses Verhalten kann nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="0e4a9-136">Es gibt keine andere Methode aus, die durch den Unterklassen (abgeleitete Klassen) erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="0e4a9-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="0e4a9-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e4a9-137">Requirements</span></span>  
 <span data-ttu-id="0e4a9-138">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e4a9-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e4a9-139">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0e4a9-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0e4a9-140">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0e4a9-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e4a9-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e4a9-141">See also</span></span>  
[<span data-ttu-id="0e4a9-142">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="0e4a9-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
