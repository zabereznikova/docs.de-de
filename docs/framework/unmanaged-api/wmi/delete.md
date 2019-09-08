---
title: Delete-Funktion (Referenz zur nicht verwalteten API)
description: Die Delete-Funktion löscht die angegebene Eigenschaft und alle zugehörigen Qualifizierer aus einer CIM-Klassendefinition.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1bf9bd5d93d1affee649588138456269411d280
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798668"
---
# <a name="delete-function"></a><span data-ttu-id="24cf5-103">Delete-Funktion</span><span class="sxs-lookup"><span data-stu-id="24cf5-103">Delete function</span></span>

<span data-ttu-id="24cf5-104">Löscht die angegebene Eigenschaft und alle zugehörigen Qualifizierer aus einer CIM-Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="24cf5-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="24cf5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="24cf5-105">Syntax</span></span>

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a><span data-ttu-id="24cf5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="24cf5-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="24cf5-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="24cf5-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="24cf5-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="24cf5-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="24cf5-109">in Der Name der zu löschenden Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="24cf5-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="24cf5-110">`wszName`muss ein Zeiger auf einen gültigen `LPCWSTR`sein.</span><span class="sxs-lookup"><span data-stu-id="24cf5-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="24cf5-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="24cf5-111">Return value</span></span>

<span data-ttu-id="24cf5-112">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="24cf5-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="24cf5-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="24cf5-113">Constant</span></span>  |<span data-ttu-id="24cf5-114">Wert</span><span class="sxs-lookup"><span data-stu-id="24cf5-114">Value</span></span>  |<span data-ttu-id="24cf5-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24cf5-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="24cf5-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="24cf5-116">0x80041001</span></span> | <span data-ttu-id="24cf5-117">Ein nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="24cf5-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="24cf5-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="24cf5-118">0x80041016</span></span> | <span data-ttu-id="24cf5-119">Die Eigenschaft kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="24cf5-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="24cf5-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="24cf5-120">0x80041008</span></span> | <span data-ttu-id="24cf5-121">`wszName` ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="24cf5-121">`wszName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="24cf5-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="24cf5-122">0x80041002</span></span> | <span data-ttu-id="24cf5-123">Die angegebene Eigenschaft ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="24cf5-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="24cf5-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="24cf5-124">0x80041006</span></span> | <span data-ttu-id="24cf5-125">Der Arbeitsspeicher reicht nicht aus, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="24cf5-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="24cf5-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="24cf5-126">0x8004101c</span></span> | <span data-ttu-id="24cf5-127">Die-Eigenschaft wird von einer Basisklasse geerbt.</span><span class="sxs-lookup"><span data-stu-id="24cf5-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="24cf5-128">Die-Eigenschaft ist eine System Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="24cf5-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="24cf5-129">0</span><span class="sxs-lookup"><span data-stu-id="24cf5-129">0</span></span> | <span data-ttu-id="24cf5-130">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="24cf5-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="24cf5-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="24cf5-131">0x80041030</span></span> | <span data-ttu-id="24cf5-132">Die Funktion löschte einen Außerkraftsetzungs Standardwert für die aktuelle Klasse.</span><span class="sxs-lookup"><span data-stu-id="24cf5-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="24cf5-133">Der Standardwert für diese Eigenschaft in der übergeordneten Klasse wurde reaktiviert.</span><span class="sxs-lookup"><span data-stu-id="24cf5-133">The default value for this property in the parent class has been reactivated.</span></span> |

## <a name="remarks"></a><span data-ttu-id="24cf5-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="24cf5-134">Remarks</span></span>

<span data-ttu-id="24cf5-135">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject::D Elete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) -Methode.</span><span class="sxs-lookup"><span data-stu-id="24cf5-135">This function wraps a call to the [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="24cf5-136">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="24cf5-136">Requirements</span></span>

<span data-ttu-id="24cf5-137">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24cf5-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="24cf5-138">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="24cf5-138">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="24cf5-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="24cf5-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="24cf5-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24cf5-140">See also</span></span>

- [<span data-ttu-id="24cf5-141">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="24cf5-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
