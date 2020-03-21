---
title: SpawnInstance-Funktion (Nicht verwaltete API-Referenz)
description: Die SpawnInstance-Funktion erstellt eine neue Instanz einer Klasse.
ms.date: 11/06/2017
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
ms.openlocfilehash: a15eb8123c1ee807444bdb4c6fe71cdccc08f434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176720"
---
# <a name="spawninstance-function"></a><span data-ttu-id="d6354-103">SpawnInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="d6354-103">SpawnInstance function</span></span>
<span data-ttu-id="d6354-104">Erstellt eine neue Instanz einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="d6354-104">Creates a new instance of a class.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="d6354-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6354-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance);
```  

## <a name="parameters"></a><span data-ttu-id="d6354-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6354-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d6354-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6354-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d6354-108">[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="d6354-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="d6354-109">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="d6354-109">[in] Reserved.</span></span> <span data-ttu-id="d6354-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="d6354-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="d6354-111">[out] Empfängt den Zeiger auf die neue Instanz der Klasse.</span><span class="sxs-lookup"><span data-stu-id="d6354-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="d6354-112">Wenn ein Fehler auftritt, wird ein `ppNewInstance` neues Objekt nicht zurückgegeben und unverändert gelassen.</span><span class="sxs-lookup"><span data-stu-id="d6354-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="d6354-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d6354-113">Return value</span></span>

<span data-ttu-id="d6354-114">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="d6354-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d6354-115">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="d6354-115">Constant</span></span>  |<span data-ttu-id="d6354-116">value</span><span class="sxs-lookup"><span data-stu-id="d6354-116">Value</span></span>  |<span data-ttu-id="d6354-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6354-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="d6354-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="d6354-118">0x80041020</span></span> | <span data-ttu-id="d6354-119">`ptr`ist keine gültige Klassendefinition und kann keine neuen Instanzen erstellen.</span><span class="sxs-lookup"><span data-stu-id="d6354-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="d6354-120">Entweder ist es unvollständig oder es wurde nicht bei der Windows-Verwaltung registriert, indem [PutClassWmi](putclasswmi.md)aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="d6354-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d6354-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d6354-121">0x80041006</span></span> | <span data-ttu-id="d6354-122">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d6354-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d6354-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d6354-123">0x80041008</span></span> | <span data-ttu-id="d6354-124">`ppNewClass` ist `null`</span><span class="sxs-lookup"><span data-stu-id="d6354-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="d6354-125">0</span><span class="sxs-lookup"><span data-stu-id="d6354-125">0</span></span> | <span data-ttu-id="d6354-126">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d6354-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d6354-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d6354-127">Remarks</span></span>

<span data-ttu-id="d6354-128">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::SpawnInstance-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance)</span><span class="sxs-lookup"><span data-stu-id="d6354-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="d6354-129">`ptr`muss eine Klassendefinition sein, die von der Windows-Verwaltung abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="d6354-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="d6354-130">(Beachten Sie, dass das Erstellen einer Instanz von einer Instanz unterstützt wird, die zurückgegebene Instanz jedoch leer ist.) Anschließend verwenden Sie diese Klassendefinition, um neue Instanzen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d6354-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="d6354-131">Wenn Sie die Instanz in die Windows-Verwaltung schreiben möchten, ist ein Aufruf der [PutInstanceWmi-Funktion](putinstancewmi.md) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d6354-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>

<span data-ttu-id="d6354-132">Das neue Objekt, das zurückgegeben wird, `ppNewClass` wird automatisch zu einer Unterklasse des aktuellen Objekts.</span><span class="sxs-lookup"><span data-stu-id="d6354-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="d6354-133">Dieses Verhalten kann nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d6354-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="d6354-134">Es gibt keine andere Methode, mit der Unterklassen (abgeleitete Klassen) erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="d6354-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="d6354-135">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d6354-135">Requirements</span></span>  
 <span data-ttu-id="d6354-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6354-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6354-137">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d6354-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d6354-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d6354-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6354-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6354-139">See also</span></span>

- [<span data-ttu-id="d6354-140">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="d6354-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
