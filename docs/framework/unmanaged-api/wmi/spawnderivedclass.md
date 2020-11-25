---
title: Spawnderivedclass-Funktion (Referenz zur nicht verwalteten API)
description: Die spawnderivedclass-Funktion erstellt ein neues-Objekt, das von einem-Objekt abgeleitet wird.
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
ms.openlocfilehash: 8020dd851b6773e6c76c53892c4b2bc21e4261bb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716511"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="0cbbc-103">SpawnDerivedClass-Funktion</span><span class="sxs-lookup"><span data-stu-id="0cbbc-103">SpawnDerivedClass function</span></span>

<span data-ttu-id="0cbbc-104">Erstellt ein neu abgeleitetes Klassenobjekt aus einem angegebenen Objekt.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-104">Creates a newly derived class object from a specified object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0cbbc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cbbc-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass);
```  

## <a name="parameters"></a><span data-ttu-id="0cbbc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0cbbc-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0cbbc-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0cbbc-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="0cbbc-109">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="0cbbc-109">[in] Reserved.</span></span> <span data-ttu-id="0cbbc-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="0cbbc-111">vorgenommen Empfängt den Zeiger auf das neue Klassen Definitions Objekt.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="0cbbc-112">Wenn ein Fehler auftritt, wird kein neues-Objekt zurückgegeben, und `ppNewClass` es bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="0cbbc-113">Der Wert darf nicht sein `null` .</span><span class="sxs-lookup"><span data-stu-id="0cbbc-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="0cbbc-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0cbbc-114">Return value</span></span>

<span data-ttu-id="0cbbc-115">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="0cbbc-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0cbbc-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="0cbbc-116">Constant</span></span>  |<span data-ttu-id="0cbbc-117">Wert</span><span class="sxs-lookup"><span data-stu-id="0cbbc-117">Value</span></span>  |<span data-ttu-id="0cbbc-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0cbbc-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="0cbbc-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0cbbc-119">0x80041001</span></span> | <span data-ttu-id="0cbbc-120">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="0cbbc-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="0cbbc-121">0x80041016</span></span> | <span data-ttu-id="0cbbc-122">Es wurde ein ungültiger Vorgang angefordert, z. b. das Erzeugen einer Klasse aus einer Instanz.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="0cbbc-123">Die Quell Klasse wurde nicht vollständig definiert oder bei der Windows-Verwaltung registriert, sodass eine neue abgeleitete Klasse nicht zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0cbbc-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0cbbc-124">0x80041006</span></span> | <span data-ttu-id="0cbbc-125">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0cbbc-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0cbbc-126">0x80041008</span></span> | <span data-ttu-id="0cbbc-127">`ppNewClass` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0cbbc-128">0</span><span class="sxs-lookup"><span data-stu-id="0cbbc-128">0</span></span> | <span data-ttu-id="0cbbc-129">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0cbbc-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0cbbc-130">Remarks</span></span>

<span data-ttu-id="0cbbc-131">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: spawnderivedclass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) -Methode.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="0cbbc-132">`ptr` muss eine Klassendefinition sein, die zur übergeordneten Klasse des erzeugten Objekts wird.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="0cbbc-133">Das zurückgegebene-Objekt wird zu einer Unterklasse des aktuellen-Objekts.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="0cbbc-134">Das neue-Objekt, das in zurückgegeben `ppNewClass` wird, wird automatisch zu einer Unterklasse des aktuellen-Objekts.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="0cbbc-135">Dieses Verhalten kann nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="0cbbc-136">Es gibt keine andere Methode, mit der Unterklassen (abgeleitete Klassen) erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="0cbbc-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="0cbbc-137">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0cbbc-137">Requirements</span></span>  

 <span data-ttu-id="0cbbc-138">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cbbc-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cbbc-139">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="0cbbc-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0cbbc-140">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0cbbc-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cbbc-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0cbbc-141">See also</span></span>

- [<span data-ttu-id="0cbbc-142">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="0cbbc-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
