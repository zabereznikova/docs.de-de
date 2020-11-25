---
title: Cloneenumwbemclassobject-Funktion (Referenz zur nicht verwalteten API)
description: Die cloneenumwbemclassobject-Funktion erstellt eine logische Kopie eines Enumerators.
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
ms.openlocfilehash: fa8a7f436c018e3e083be452d300eb21e17f93f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708126"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="f0fad-103">CloneEnumWbemClassObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="f0fad-103">CloneEnumWbemClassObject function</span></span>

<span data-ttu-id="f0fad-104">Erstellt eine logische Kopie eines Enumerators unter Beibehaltung der aktuellen Position in einer Enumeration.</span><span class="sxs-lookup"><span data-stu-id="f0fad-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="f0fad-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0fad-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="f0fad-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0fad-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="f0fad-107">vorgenommen Empfängt einen Zeiger auf ein neues [ienumwbemclassobject-Objekt](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="f0fad-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="f0fad-108">in Die Autorisierungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="f0fad-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="f0fad-109">in Die Ebene des Identitäts Wechsels.</span><span class="sxs-lookup"><span data-stu-id="f0fad-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="f0fad-110">vorgenommen Ein Zeiger auf die Instanz von [ienumwbemclassobject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) , die geklont werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0fad-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="f0fad-111">in Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="f0fad-111">[in] The user name.</span></span> <span data-ttu-id="f0fad-112">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="f0fad-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="f0fad-113">in Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="f0fad-113">[in] The password.</span></span> <span data-ttu-id="f0fad-114">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="f0fad-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="f0fad-115">in Der Domänen Name des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="f0fad-115">[in] The domain name of the user.</span></span> <span data-ttu-id="f0fad-116">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="f0fad-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="f0fad-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f0fad-117">Return value</span></span>

<span data-ttu-id="f0fad-118">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="f0fad-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f0fad-119">Konstante</span><span class="sxs-lookup"><span data-stu-id="f0fad-119">Constant</span></span>  |<span data-ttu-id="f0fad-120">Wert</span><span class="sxs-lookup"><span data-stu-id="f0fad-120">Value</span></span>  |<span data-ttu-id="f0fad-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f0fad-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="f0fad-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="f0fad-122">0x80041001</span></span> | <span data-ttu-id="f0fad-123">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f0fad-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f0fad-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f0fad-124">0x80041008</span></span> | <span data-ttu-id="f0fad-125">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="f0fad-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f0fad-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f0fad-126">0x80041006</span></span> | <span data-ttu-id="f0fad-127">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f0fad-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="f0fad-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="f0fad-128">0x80041015</span></span> | <span data-ttu-id="f0fad-129">Fehler beim Remote Prozedur Aufruf (RPC)-Link zwischen dem aktuellen Prozess und WMI.</span><span class="sxs-lookup"><span data-stu-id="f0fad-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f0fad-130">0</span><span class="sxs-lookup"><span data-stu-id="f0fad-130">0</span></span> | <span data-ttu-id="f0fad-131">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="f0fad-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="f0fad-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0fad-132">Remarks</span></span>

<span data-ttu-id="f0fad-133">Diese Funktion umschließt einen Aufrufe der [ienumwbemclassobject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) -Methode.</span><span class="sxs-lookup"><span data-stu-id="f0fad-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="f0fad-134">Mit dieser Methode wird nur eine "bestmögliche" Kopie erstellt.</span><span class="sxs-lookup"><span data-stu-id="f0fad-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="f0fad-135">Aufgrund der dynamischen Natur vieler CIM-Objekte ist es möglich, dass der neue Enumerator nicht denselben Satz von Objekten aufzählt wie der Quell Enumerator.</span><span class="sxs-lookup"><span data-stu-id="f0fad-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="f0fad-136">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo](geterrorinfo.md) -Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f0fad-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="f0fad-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0fad-137">Example</span></span>

<span data-ttu-id="f0fad-138">Ein Beispiel finden Sie unter der [ienumwbemclassobject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) -Methode.</span><span class="sxs-lookup"><span data-stu-id="f0fad-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0fad-139">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f0fad-139">Requirements</span></span>

 <span data-ttu-id="f0fad-140">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0fad-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="f0fad-141">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="f0fad-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="f0fad-142">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f0fad-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f0fad-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0fad-143">See also</span></span>

- [<span data-ttu-id="f0fad-144">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="f0fad-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
