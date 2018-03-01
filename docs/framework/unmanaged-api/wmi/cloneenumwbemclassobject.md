---
title: CloneEnumWbemClassObject-Funktion (Referenz zur nicht verwalteten API)
description: Die CloneEnumWbemClassObject-Funktion macht eine logische Kopie eines Enumerators.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 22bcf2731ff682bf538858fc66a7a94be7f5d7df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="1eaa3-103">CloneEnumWbemClassObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="1eaa3-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="1eaa3-104">Erstellt eine logische Kopie eines Enumerators, der seiner aktuellen Position in einer Enumeration beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="1eaa3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1eaa3-105">Syntax</span></span>  
  
```  
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```  

## <a name="parameters"></a><span data-ttu-id="1eaa3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1eaa3-106">Parameters</span></span>

`ppEnum`  
<span data-ttu-id="1eaa3-107">[out] Empfängt einen Zeiger auf eine neue [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="1eaa3-107">[out] Receives a pointer to a new [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span></span>

`authLevel`  
<span data-ttu-id="1eaa3-108">[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-108">[in] The authorization level.</span></span>

<span data-ttu-id="1eaa3-109">`impLevel`[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-109">`impLevel` [in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`  
<span data-ttu-id="1eaa3-110">[out] Ein Zeiger auf die [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) Instanz, geklont zu werden.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-110">[out] A pointer to the [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) instance to be cloned.</span></span>

`strUser`   
<span data-ttu-id="1eaa3-111">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-111">[in] The user name.</span></span> <span data-ttu-id="1eaa3-112">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="1eaa3-113">[in] Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-113">[in] The password.</span></span> <span data-ttu-id="1eaa3-114">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="1eaa3-115">[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-115">[in] The domain name of the user.</span></span> <span data-ttu-id="1eaa3-116">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="1eaa3-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1eaa3-117">Return value</span></span>

<span data-ttu-id="1eaa3-118">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="1eaa3-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1eaa3-119">Konstante</span><span class="sxs-lookup"><span data-stu-id="1eaa3-119">Constant</span></span>  |<span data-ttu-id="1eaa3-120">Wert</span><span class="sxs-lookup"><span data-stu-id="1eaa3-120">Value</span></span>  |<span data-ttu-id="1eaa3-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1eaa3-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="1eaa3-122">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="1eaa3-122">0x80041001</span></span> | <span data-ttu-id="1eaa3-123">Ein allgemeiner Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1eaa3-124">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="1eaa3-124">0x80041008</span></span> | <span data-ttu-id="1eaa3-125">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1eaa3-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1eaa3-126">0x80041006</span></span> | <span data-ttu-id="1eaa3-127">Ist nicht genügend Arbeitsspeicher verfügbar, der Vorgang abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="1eaa3-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="1eaa3-128">0x80041015</span></span> | <span data-ttu-id="1eaa3-129">Der Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-ausgefallen ist.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="1eaa3-130">0</span><span class="sxs-lookup"><span data-stu-id="1eaa3-130">0</span></span> | <span data-ttu-id="1eaa3-131">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1eaa3-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1eaa3-132">Remarks</span></span>

<span data-ttu-id="1eaa3-133">Diese Funktion dient als Wrapper für einen Aufruf der [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-133">This function wraps a call to the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="1eaa3-134">Bei dieser Methode ist nur eine Kopie "best-Effort".</span><span class="sxs-lookup"><span data-stu-id="1eaa3-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="1eaa3-135">Aufgrund der dynamischen Natur der viele CIM-Objekte ist es möglich, dass der neue Enumerator nicht den gleichen Satz von Objekten wie der Quell-Enumerator aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>  

<span data-ttu-id="1eaa3-136">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch Aufrufen der [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="1eaa3-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1eaa3-137">Example</span></span>

<span data-ttu-id="1eaa3-138">Ein Beispiel finden Sie die [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="1eaa3-138">For an example, see the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1eaa3-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1eaa3-139">Requirements</span></span>  
 <span data-ttu-id="1eaa3-140">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1eaa3-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eaa3-141">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1eaa3-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1eaa3-142">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1eaa3-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eaa3-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1eaa3-143">See also</span></span>  
[<span data-ttu-id="1eaa3-144">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="1eaa3-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
