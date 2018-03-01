---
title: SpawnInstance-Funktion (Referenz zur nicht verwalteten API)
description: Die SpawnInstance-Funktion erstellt eine neue Instanz einer Klasse.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 68508f3000e7f4ac481f940ef4c715366c37125c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="spawninstance-function"></a><span data-ttu-id="02a1a-103">SpawnInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="02a1a-103">SpawnInstance function</span></span>
<span data-ttu-id="02a1a-104">Erstellt eine neue Instanz einer Klasse an.</span><span class="sxs-lookup"><span data-stu-id="02a1a-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="02a1a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="02a1a-105">Syntax</span></span>  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="02a1a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="02a1a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="02a1a-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="02a1a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="02a1a-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="02a1a-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="02a1a-109">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="02a1a-109">[in] Reserved.</span></span> <span data-ttu-id="02a1a-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="02a1a-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="02a1a-111">[out] Erhält der Zeiger auf die neue Instanz der Klasse.</span><span class="sxs-lookup"><span data-stu-id="02a1a-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="02a1a-112">Wenn ein Fehler auftritt, wird ein neues Objekt nicht zurückgegeben, und `ppNewInstance` ist der linke unverändert bleiben sollen.</span><span class="sxs-lookup"><span data-stu-id="02a1a-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="02a1a-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="02a1a-113">Return value</span></span>

<span data-ttu-id="02a1a-114">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="02a1a-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="02a1a-115">Konstante</span><span class="sxs-lookup"><span data-stu-id="02a1a-115">Constant</span></span>  |<span data-ttu-id="02a1a-116">Wert</span><span class="sxs-lookup"><span data-stu-id="02a1a-116">Value</span></span>  |<span data-ttu-id="02a1a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02a1a-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="02a1a-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="02a1a-118">0x80041020</span></span> | <span data-ttu-id="02a1a-119">`ptr`ist keine gültige Klassendefinition, und neue Instanzen können nicht erzeugen.</span><span class="sxs-lookup"><span data-stu-id="02a1a-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="02a1a-120">Entweder ist es unvollständig, oder er wurde nicht mit Windows Management registriert wurde, durch Aufrufen [PutClassWmi](putclasswmi.md).</span><span class="sxs-lookup"><span data-stu-id="02a1a-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="02a1a-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="02a1a-121">0x80041006</span></span> | <span data-ttu-id="02a1a-122">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="02a1a-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="02a1a-123">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="02a1a-123">0x80041008</span></span> | <span data-ttu-id="02a1a-124">`ppNewClass` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="02a1a-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="02a1a-125">0</span><span class="sxs-lookup"><span data-stu-id="02a1a-125">0</span></span> | <span data-ttu-id="02a1a-126">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="02a1a-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="02a1a-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02a1a-127">Remarks</span></span>

<span data-ttu-id="02a1a-128">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject:: SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="02a1a-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="02a1a-129">`ptr`eine Definition einer Klasse muss aus der Verwaltung von Windows abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="02a1a-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="02a1a-130">(Beachten Sie, dass das Erstellen einer Instanz von einer Instanz unterstützt wird, aber die zurückgegebene Instanz ist leer.) Anschließend verwenden Sie diese Klassendefinition, um neue Instanzen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="02a1a-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="02a1a-131">Ein Aufruf der [PutInstanceWmi](putinstancewmi.md) Funktion ist erforderlich, wenn Sie beabsichtigen, das Schreiben der Instanz zur Windows-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="02a1a-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>




<span data-ttu-id="02a1a-132">Das neue Objekt im zurückgegebenen `ppNewClass` wird automatisch eine Unterklasse des aktuellen Objekts.</span><span class="sxs-lookup"><span data-stu-id="02a1a-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="02a1a-133">Dieses Verhalten kann nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="02a1a-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="02a1a-134">Es gibt keine andere Methode aus, die durch den Unterklassen (abgeleitete Klassen) erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="02a1a-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="02a1a-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="02a1a-135">Requirements</span></span>  
 <span data-ttu-id="02a1a-136">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02a1a-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02a1a-137">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="02a1a-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="02a1a-138">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="02a1a-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02a1a-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02a1a-139">See also</span></span>  
[<span data-ttu-id="02a1a-140">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="02a1a-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
