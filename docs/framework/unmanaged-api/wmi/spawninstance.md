---
title: SpawnInstance-Funktion (Referenz zur nicht verwalteten API)
description: Die SpawnInstance-Funktion erstellt eine neue Instanz einer-Klasse.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 529905bd9286520a8e09479bfc95ef0b614f53e9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798222"
---
# <a name="spawninstance-function"></a><span data-ttu-id="8fef4-103">SpawnInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="8fef4-103">SpawnInstance function</span></span>
<span data-ttu-id="8fef4-104">Erstellt eine neue Instanz einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="8fef4-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8fef4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8fef4-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="8fef4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8fef4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8fef4-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="8fef4-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8fef4-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="8fef4-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="8fef4-109">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="8fef4-109">[in] Reserved.</span></span> <span data-ttu-id="8fef4-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="8fef4-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="8fef4-111">vorgenommen Empfängt den Zeiger auf die neue Instanz der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8fef4-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="8fef4-112">Wenn ein Fehler auftritt, wird kein neues-Objekt zurückgegeben, `ppNewInstance` und es bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="8fef4-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="8fef4-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8fef4-113">Return value</span></span>

<span data-ttu-id="8fef4-114">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="8fef4-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8fef4-115">Konstante</span><span class="sxs-lookup"><span data-stu-id="8fef4-115">Constant</span></span>  |<span data-ttu-id="8fef4-116">Wert</span><span class="sxs-lookup"><span data-stu-id="8fef4-116">Value</span></span>  |<span data-ttu-id="8fef4-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fef4-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="8fef4-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="8fef4-118">0x80041020</span></span> | <span data-ttu-id="8fef4-119">`ptr`ist keine gültige Klassendefinition und kann keine neuen Instanzen erzeugen.</span><span class="sxs-lookup"><span data-stu-id="8fef4-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="8fef4-120">Sie ist entweder unvollständig oder wurde nicht bei der Windows-Verwaltung durch Aufrufen von [putclasswmi](putclasswmi.md)registriert.</span><span class="sxs-lookup"><span data-stu-id="8fef4-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8fef4-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8fef4-121">0x80041006</span></span> | <span data-ttu-id="8fef4-122">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="8fef4-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8fef4-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8fef4-123">0x80041008</span></span> | <span data-ttu-id="8fef4-124">`ppNewClass` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="8fef4-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="8fef4-125">0</span><span class="sxs-lookup"><span data-stu-id="8fef4-125">0</span></span> | <span data-ttu-id="8fef4-126">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8fef4-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8fef4-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8fef4-127">Remarks</span></span>

<span data-ttu-id="8fef4-128">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) -Methode.</span><span class="sxs-lookup"><span data-stu-id="8fef4-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="8fef4-129">`ptr`muss eine Klassendefinition sein, die von der Windows-Verwaltung abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8fef4-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="8fef4-130">(Beachten Sie, dass das Erzeugen einer Instanz aus einer-Instanz unterstützt wird, aber die zurückgegebene-Instanz leer ist.) Anschließend verwenden Sie diese Klassendefinition, um neue Instanzen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8fef4-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="8fef4-131">Wenn Sie beabsichtigen, die Instanz in die Windows-Verwaltung zu schreiben, ist ein Rückruf der [putinstancewmi](putinstancewmi.md) -Funktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8fef4-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>

<span data-ttu-id="8fef4-132">Das neue-Objekt, `ppNewClass` das in zurückgegeben wird, wird automatisch zu einer Unterklasse des aktuellen-Objekts.</span><span class="sxs-lookup"><span data-stu-id="8fef4-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="8fef4-133">Dieses Verhalten kann nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="8fef4-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="8fef4-134">Es gibt keine andere Methode, mit der Unterklassen (abgeleitete Klassen) erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="8fef4-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="8fef4-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8fef4-135">Requirements</span></span>  
 <span data-ttu-id="8fef4-136">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fef4-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fef4-137">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8fef4-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8fef4-138">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8fef4-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fef4-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fef4-139">See also</span></span>

- [<span data-ttu-id="8fef4-140">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="8fef4-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
