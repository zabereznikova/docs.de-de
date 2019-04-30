---
title: CloneEnumWbemClassObject-Funktion (Referenz zur nicht verwalteten API)
description: CloneEnumWbemClassObject-Funktion ist eine logische Kopie eines Enumerators.
ms.date: 11/06/2017
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
ms.openlocfilehash: ac85ed86ea968fa945e07f95db8977a33c5d12a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968167"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="cef9a-103">CloneEnumWbemClassObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="cef9a-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="cef9a-104">Erstellt eine logische Kopie eines Enumerators unter Beibehaltung der aktuellen Position in einer Enumeration.</span><span class="sxs-lookup"><span data-stu-id="cef9a-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="cef9a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cef9a-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="cef9a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="cef9a-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="cef9a-107">[out] Erhält einen Zeiger auf ein neues [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="cef9a-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="cef9a-108">[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="cef9a-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="cef9a-109">[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="cef9a-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="cef9a-110">[out] Ein Zeiger auf die [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) Instanz, geklont zu werden.</span><span class="sxs-lookup"><span data-stu-id="cef9a-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="cef9a-111">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="cef9a-111">[in] The user name.</span></span> <span data-ttu-id="cef9a-112">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="cef9a-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="cef9a-113">[in] Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="cef9a-113">[in] The password.</span></span> <span data-ttu-id="cef9a-114">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="cef9a-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="cef9a-115">`strAuthority`\ [in] der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="cef9a-115">`strAuthority`\ [in] The domain name of the user.</span></span> <span data-ttu-id="cef9a-116">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="cef9a-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="cef9a-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cef9a-117">Return value</span></span>

<span data-ttu-id="cef9a-118">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="cef9a-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cef9a-119">Konstante</span><span class="sxs-lookup"><span data-stu-id="cef9a-119">Constant</span></span>  |<span data-ttu-id="cef9a-120">Wert</span><span class="sxs-lookup"><span data-stu-id="cef9a-120">Value</span></span>  |<span data-ttu-id="cef9a-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cef9a-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="cef9a-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="cef9a-122">0x80041001</span></span> | <span data-ttu-id="cef9a-123">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="cef9a-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="cef9a-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="cef9a-124">0x80041008</span></span> | <span data-ttu-id="cef9a-125">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="cef9a-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="cef9a-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="cef9a-126">0x80041006</span></span> | <span data-ttu-id="cef9a-127">Ist nicht genügend Arbeitsspeicher verfügbar, der Vorgang abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="cef9a-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="cef9a-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="cef9a-128">0x80041015</span></span> | <span data-ttu-id="cef9a-129">Der Remoteprozeduraufruf-Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-hat Fehler.</span><span class="sxs-lookup"><span data-stu-id="cef9a-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="cef9a-130">0</span><span class="sxs-lookup"><span data-stu-id="cef9a-130">0</span></span> | <span data-ttu-id="cef9a-131">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="cef9a-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="cef9a-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cef9a-132">Remarks</span></span>

<span data-ttu-id="cef9a-133">Diese Funktion umschließt einen Aufruf der [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) Methode.</span><span class="sxs-lookup"><span data-stu-id="cef9a-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="cef9a-134">Auf diese Weise wird nur eine "best-Effort" kopieren.</span><span class="sxs-lookup"><span data-stu-id="cef9a-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="cef9a-135">Aufgrund der dynamischen Natur der viele CIM-Objekte werden soll ist es möglich, dass der neue Enumerator nicht den gleichen Satz von Objekten als Enumerator aus Quelle aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="cef9a-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="cef9a-136">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch den Aufruf der [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="cef9a-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="cef9a-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cef9a-137">Example</span></span>

<span data-ttu-id="cef9a-138">Ein Beispiel finden Sie unter den [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) Methode.</span><span class="sxs-lookup"><span data-stu-id="cef9a-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="cef9a-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cef9a-139">Requirements</span></span>
 <span data-ttu-id="cef9a-140">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cef9a-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="cef9a-141">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="cef9a-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="cef9a-142">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cef9a-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cef9a-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cef9a-143">See also</span></span>

- [<span data-ttu-id="cef9a-144">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="cef9a-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)