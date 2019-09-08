---
title: Getpropertyqualifierset-Funktion (Referenz zur nicht verwalteten API)
description: Die getpropertyqualifierset-Funktion Ruft den Qualifizierer Satz für eine Eigenschaft ab.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7bce241d10051e4c6be94cdfa40de23773fb0bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798472"
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="6bc35-103">Getpropertyqualifierset-Funktion</span><span class="sxs-lookup"><span data-stu-id="6bc35-103">GetPropertyQualifierSet function</span></span>

<span data-ttu-id="6bc35-104">Ruft den Qualifizierer ab, der für eine bestimmte Eigenschaft festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6bc35-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="6bc35-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6bc35-105">Syntax</span></span>

```cpp
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="6bc35-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6bc35-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="6bc35-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="6bc35-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="6bc35-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="6bc35-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="6bc35-109">in Der Eigenschaftsname.</span><span class="sxs-lookup"><span data-stu-id="6bc35-109">[in] The property  name.</span></span> <span data-ttu-id="6bc35-110">`wszProperty`muss auf einen gültigen `LPCWSTR`zeigen.</span><span class="sxs-lookup"><span data-stu-id="6bc35-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="6bc35-111">vorgenommen Empfängt den Schnittstellen Zeiger, der den Zugriff auf die Qualifizierer der Eigenschaft zulässt.</span><span class="sxs-lookup"><span data-stu-id="6bc35-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="6bc35-112">`ppQualSet` darf nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="6bc35-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="6bc35-113">Wenn ein Fehler auftritt, wird kein neues Objekt zurückgegeben, und der Zeiger wird so festgelegt, `null`dass er auf verweist.</span><span class="sxs-lookup"><span data-stu-id="6bc35-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="6bc35-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6bc35-114">Return value</span></span>

<span data-ttu-id="6bc35-115">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="6bc35-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6bc35-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="6bc35-116">Constant</span></span>  |<span data-ttu-id="6bc35-117">Wert</span><span class="sxs-lookup"><span data-stu-id="6bc35-117">Value</span></span>  |<span data-ttu-id="6bc35-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6bc35-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="6bc35-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="6bc35-119">0x80041001</span></span> | <span data-ttu-id="6bc35-120">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6bc35-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="6bc35-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="6bc35-121">0x80041002</span></span> | <span data-ttu-id="6bc35-122">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6bc35-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6bc35-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6bc35-123">0x80041006</span></span> | <span data-ttu-id="6bc35-124">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6bc35-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6bc35-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6bc35-125">0x80041008</span></span> | <span data-ttu-id="6bc35-126">Ein-Parameter `null`ist.</span><span class="sxs-lookup"><span data-stu-id="6bc35-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="6bc35-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="6bc35-127">0x80041030</span></span> | <span data-ttu-id="6bc35-128">Die Funktion versucht, Qualifizierer einer System Eigenschaft zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6bc35-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="6bc35-129">0</span><span class="sxs-lookup"><span data-stu-id="6bc35-129">0</span></span> | <span data-ttu-id="6bc35-130">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="6bc35-130">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="6bc35-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6bc35-131">Remarks</span></span>

<span data-ttu-id="6bc35-132">Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: getpropertyqualifierset](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) -Methode.</span><span class="sxs-lookup"><span data-stu-id="6bc35-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) method.</span></span>

<span data-ttu-id="6bc35-133">Ein Aufrufe dieser Funktion wird nur unterstützt, wenn das aktuelle Objekt eine CIM-Klassendefinition ist.</span><span class="sxs-lookup"><span data-stu-id="6bc35-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="6bc35-134">Die Methoden Bearbeitung ist für [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Zeiger, die auf CIM-Instanzen verweisen, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6bc35-134">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="6bc35-135">Da jede Methode über eigene Qualifizierer verfügen kann, ermöglicht der [iwbemqualifierset-Zeiger dem Aufrufer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) , diese Qualifizierer hinzuzufügen, zu bearbeiten oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="6bc35-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="6bc35-136">Da Systemeigenschaften keine Qualifizierer aufweisen, gibt `WBEM_E_SYSTEM_PROPERTY` die Funktion zurück, wenn Sie versuchen, einen [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Zeiger für eine System Eigenschaft abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6bc35-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="6bc35-137">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6bc35-137">Requirements</span></span>

<span data-ttu-id="6bc35-138">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bc35-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="6bc35-139">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6bc35-139">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="6bc35-140">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6bc35-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6bc35-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bc35-141">See also</span></span>

- [<span data-ttu-id="6bc35-142">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="6bc35-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
