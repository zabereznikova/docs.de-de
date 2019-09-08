---
title: Getmethodqualifierset-Funktion (Referenz zur nicht verwalteten API)
description: Die getmethodqualifierset-Funktion Ruft den Qualifizierer Satz einer Methode ab.
ms.date: 11/06/2017
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86a7788736c3c12cfcfd405de88dfadfb14c1eca
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798529"
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="e1867-103">GetMethodQualifierSet-Funktion</span><span class="sxs-lookup"><span data-stu-id="e1867-103">GetMethodQualifierSet function</span></span>

<span data-ttu-id="e1867-104">Ruft den Qualifizierer ab, der für eine bestimmte Methode festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e1867-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e1867-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1867-105">Syntax</span></span>

```cpp
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="e1867-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e1867-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="e1867-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1867-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="e1867-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="e1867-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="e1867-109">in Der Methodenname.</span><span class="sxs-lookup"><span data-stu-id="e1867-109">[in] The method  name.</span></span> <span data-ttu-id="e1867-110">`wszMethod`muss auf einen gültigen `LPCWSTR`zeigen.</span><span class="sxs-lookup"><span data-stu-id="e1867-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="e1867-111">vorgenommen Empfängt den Schnittstellen Zeiger, der den Zugriff auf die Qualifizierer der Methode zulässt.</span><span class="sxs-lookup"><span data-stu-id="e1867-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="e1867-112">`ppQualSet` darf nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="e1867-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="e1867-113">Wenn ein Fehler auftritt, wird kein neues Objekt zurückgegeben, und der Zeiger wird so festgelegt, `null`dass er auf verweist.</span><span class="sxs-lookup"><span data-stu-id="e1867-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="e1867-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e1867-114">Return value</span></span>

<span data-ttu-id="e1867-115">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="e1867-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e1867-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="e1867-116">Constant</span></span>  |<span data-ttu-id="e1867-117">Wert</span><span class="sxs-lookup"><span data-stu-id="e1867-117">Value</span></span>  |<span data-ttu-id="e1867-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1867-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="e1867-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e1867-119">0x80041002</span></span> | <span data-ttu-id="e1867-120">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e1867-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e1867-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e1867-121">0x80041008</span></span> | <span data-ttu-id="e1867-122">Ein-Parameter `null`ist.</span><span class="sxs-lookup"><span data-stu-id="e1867-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e1867-123">0</span><span class="sxs-lookup"><span data-stu-id="e1867-123">0</span></span> | <span data-ttu-id="e1867-124">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="e1867-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="e1867-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1867-125">Remarks</span></span>

<span data-ttu-id="e1867-126">Diese Funktion umschließt einen Aufruf der [IWbemClassObject:: getmethodqualifierset](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) -Methode.</span><span class="sxs-lookup"><span data-stu-id="e1867-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) method.</span></span>

<span data-ttu-id="e1867-127">Ein Aufrufe dieser Funktion wird nur unterstützt, wenn das aktuelle Objekt eine CIM-Klassendefinition ist.</span><span class="sxs-lookup"><span data-stu-id="e1867-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="e1867-128">Die Methoden Bearbeitung ist für [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Zeiger, die auf CIM-Instanzen verweisen, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e1867-128">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="e1867-129">Da jede Methode über eigene Qualifizierer verfügen kann, ermöglicht der [iwbemqualifierset-Zeiger dem Aufrufer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) , diese Qualifizierer hinzuzufügen, zu bearbeiten oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e1867-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="e1867-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e1867-130">Requirements</span></span>

<span data-ttu-id="e1867-131">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1867-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e1867-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e1867-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="e1867-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e1867-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e1867-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1867-134">See also</span></span>

- [<span data-ttu-id="e1867-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="e1867-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
