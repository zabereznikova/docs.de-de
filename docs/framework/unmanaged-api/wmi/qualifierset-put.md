---
title: QualifierSet_Put-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_Put-Funktion schreibt den benannten Qualifizierer und seinen Wert.
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 40688a0e4273233245d00fcd927f95945a43f712
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798273"
---
# <a name="qualifierset_put-function"></a><span data-ttu-id="38e0e-103">QualifierSet_Put-Funktion</span><span class="sxs-lookup"><span data-stu-id="38e0e-103">QualifierSet_Put function</span></span>

<span data-ttu-id="38e0e-104">Schreibt den benannten Qualifizierer und den Wert.</span><span class="sxs-lookup"><span data-stu-id="38e0e-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="38e0e-105">Der neue Qualifizierer überschreibt den vorherigen Wert desselben Namens.</span><span class="sxs-lookup"><span data-stu-id="38e0e-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="38e0e-106">Wenn der Qualifizierer nicht vorhanden ist, wird er erstellt.</span><span class="sxs-lookup"><span data-stu-id="38e0e-106">If the qualifier does not exist, it is created.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="38e0e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="38e0e-107">Syntax</span></span>

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="38e0e-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="38e0e-108">Parameters</span></span>

`vFunc`\
<span data-ttu-id="38e0e-109">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="38e0e-109">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="38e0e-110">in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="38e0e-110">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`\
<span data-ttu-id="38e0e-111">in Der Name des Qualifizierers, der geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="38e0e-111">[in] The name of the qualifier to write.</span></span>

`pVal`\
<span data-ttu-id="38e0e-112">in Ein Zeiger auf einen gültigen `VARIANT` , der den Qualifizierer enthält, der geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="38e0e-112">[in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="38e0e-113">Dieser Parameter darf nicht `null`sein.</span><span class="sxs-lookup"><span data-stu-id="38e0e-113">This parameter cannot be `null`.</span></span>

`lFlavor`\
<span data-ttu-id="38e0e-114">in Eine der folgenden Konstanten, die die gewünschten qualifizierervarianten für diesen Qualifizierer definiert.</span><span class="sxs-lookup"><span data-stu-id="38e0e-114">[in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="38e0e-115">Der Standardwert ist `WBEM_FLAVOR_OVERRIDABLE` (0).</span><span class="sxs-lookup"><span data-stu-id="38e0e-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="38e0e-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="38e0e-116">Constant</span></span>  |<span data-ttu-id="38e0e-117">Wert</span><span class="sxs-lookup"><span data-stu-id="38e0e-117">Value</span></span>  |<span data-ttu-id="38e0e-118">Description</span><span class="sxs-lookup"><span data-stu-id="38e0e-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="38e0e-119">0</span><span class="sxs-lookup"><span data-stu-id="38e0e-119">0</span></span> | <span data-ttu-id="38e0e-120">Der Qualifizierer kann in einer abgeleiteten Klasse oder Instanz überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="38e0e-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="38e0e-121">**Dies ist der Standardwert.**</span><span class="sxs-lookup"><span data-stu-id="38e0e-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="38e0e-122">1</span><span class="sxs-lookup"><span data-stu-id="38e0e-122">1</span></span> | <span data-ttu-id="38e0e-123">Der Qualifizierer wird an Instanzen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="38e0e-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="38e0e-124">2</span><span class="sxs-lookup"><span data-stu-id="38e0e-124">2</span></span> | <span data-ttu-id="38e0e-125">Der Qualifizierer wird an abgeleitete Klassen weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="38e0e-125">The qualifier is propagated to derived classes.</span></span> |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | <span data-ttu-id="38e0e-126">0x10</span><span class="sxs-lookup"><span data-stu-id="38e0e-126">0x10</span></span> | <span data-ttu-id="38e0e-127">Der Qualifizierer kann in einer abgeleiteten Klasse oder Instanz nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="38e0e-127">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| `WBEM_FLAVOR_AMENDED` | <span data-ttu-id="38e0e-128">0x80</span><span class="sxs-lookup"><span data-stu-id="38e0e-128">0x80</span></span> | <span data-ttu-id="38e0e-129">Der Qualifizierer ist lokalisiert.</span><span class="sxs-lookup"><span data-stu-id="38e0e-129">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="38e0e-130">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="38e0e-130">Return value</span></span>

<span data-ttu-id="38e0e-131">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="38e0e-131">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="38e0e-132">Konstante</span><span class="sxs-lookup"><span data-stu-id="38e0e-132">Constant</span></span>  |<span data-ttu-id="38e0e-133">Wert</span><span class="sxs-lookup"><span data-stu-id="38e0e-133">Value</span></span>  |<span data-ttu-id="38e0e-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38e0e-134">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="38e0e-135">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="38e0e-135">0x8004101f</span></span> | <span data-ttu-id="38e0e-136">Es wurde ein unzulässiger Versuch unternommen, den **Schlüssel** Qualifizierer für eine Eigenschaft anzugeben, die kein Schlüssel sein kann.</span><span class="sxs-lookup"><span data-stu-id="38e0e-136">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="38e0e-137">Die Schlüssel werden in der Klassendefinition für ein Objekt angegeben und können nicht pro Instanz geändert werden.</span><span class="sxs-lookup"><span data-stu-id="38e0e-137">The keys are specified in the class definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="38e0e-138">0x80041008</span><span class="sxs-lookup"><span data-stu-id="38e0e-138">0x80041008</span></span> | <span data-ttu-id="38e0e-139">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="38e0e-139">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="38e0e-140">0x80041029</span><span class="sxs-lookup"><span data-stu-id="38e0e-140">0x80041029</span></span> | <span data-ttu-id="38e0e-141">Der `pVal` -Parameter ist kein gültiger qualifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="38e0e-141">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="38e0e-142">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="38e0e-142">0x8004101a</span></span> | <span data-ttu-id="38e0e-143">Es ist nicht möglich, die `QualifierSet_Put` -Methode für den Qualifizierer aufzurufen, da das besitzende Objekt keine über schreibungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="38e0e-143">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="38e0e-144">0</span><span class="sxs-lookup"><span data-stu-id="38e0e-144">0</span></span> | <span data-ttu-id="38e0e-145">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="38e0e-145">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="38e0e-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="38e0e-146">Remarks</span></span>

<span data-ttu-id="38e0e-147">Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) -Methode.</span><span class="sxs-lookup"><span data-stu-id="38e0e-147">This function wraps a call to the [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="38e0e-148">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="38e0e-148">Requirements</span></span>

<span data-ttu-id="38e0e-149">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38e0e-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="38e0e-150">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="38e0e-150">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="38e0e-151">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="38e0e-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="38e0e-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38e0e-152">See also</span></span>

- [<span data-ttu-id="38e0e-153">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="38e0e-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
