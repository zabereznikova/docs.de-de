---
title: QualifierSet_Delete-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_Delete-Funktion löscht einen Qualifizierer anhand des Namens.
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 2000de77903c3dabb43116fa1700b4ed393aeb5a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721152"
---
# <a name="qualifierset_delete-function"></a><span data-ttu-id="a6c70-103">QualifierSet_Delete-Funktion</span><span class="sxs-lookup"><span data-stu-id="a6c70-103">QualifierSet_Delete function</span></span>

<span data-ttu-id="a6c70-104">Löscht einen angegebenen Qualifizierer anhand des Namens.</span><span class="sxs-lookup"><span data-stu-id="a6c70-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a6c70-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6c70-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="a6c70-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6c70-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="a6c70-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6c70-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="a6c70-108">`ptr` in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="a6c70-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="a6c70-109">`wszName` in Der Name des zu löschenden Qualifizierers.</span><span class="sxs-lookup"><span data-stu-id="a6c70-109">`wszName` [in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="a6c70-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a6c70-110">Return value</span></span>

<span data-ttu-id="a6c70-111">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="a6c70-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a6c70-112">Konstante</span><span class="sxs-lookup"><span data-stu-id="a6c70-112">Constant</span></span>  |<span data-ttu-id="a6c70-113">Wert</span><span class="sxs-lookup"><span data-stu-id="a6c70-113">Value</span></span>  |<span data-ttu-id="a6c70-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a6c70-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a6c70-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a6c70-115">0x80041008</span></span> | <span data-ttu-id="a6c70-116">Der `wszName`-Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="a6c70-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="a6c70-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="a6c70-117">0x80041016</span></span> | <span data-ttu-id="a6c70-118">Das Löschen dieses Qualifizierers ist unzulässig.</span><span class="sxs-lookup"><span data-stu-id="a6c70-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="a6c70-119">0x80041002 angezeigt</span><span class="sxs-lookup"><span data-stu-id="a6c70-119">0x80041002</span></span> | <span data-ttu-id="a6c70-120">Der angegebene Qualifizierer wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="a6c70-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a6c70-121">0</span><span class="sxs-lookup"><span data-stu-id="a6c70-121">0</span></span> | <span data-ttu-id="a6c70-122">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="a6c70-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="a6c70-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="a6c70-123">0x40002</span></span> | <span data-ttu-id="a6c70-124">Die lokale außer Kraft Setzung wurde gelöscht, und der ursprüngliche Qualifizierer aus dem übergeordneten Objekt wurde fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a6c70-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="a6c70-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6c70-125">Remarks</span></span>

<span data-ttu-id="a6c70-126">Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset::D Elete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) -Methode.</span><span class="sxs-lookup"><span data-stu-id="a6c70-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="a6c70-127">Aufgrund von qualifizierungsweitergaberegeln wurde ein bestimmter Qualifizierer möglicherweise von einem anderen Objekt geerbt und nur in der aktuellen Klasse oder Instanz überschrieben.</span><span class="sxs-lookup"><span data-stu-id="a6c70-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="a6c70-128">In diesem Fall setzt die- `QualifierSet_Delete` Methode den-Qualifizierer auf seinen ursprünglichen geerbten Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a6c70-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="a6c70-129">Die-Funktion gibt in diesem Fall den Statuscode zurück `WBEM_S_RESET_TO_DEFAULT` .</span><span class="sxs-lookup"><span data-stu-id="a6c70-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="a6c70-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a6c70-130">Requirements</span></span>  

 <span data-ttu-id="a6c70-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6c70-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6c70-132">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="a6c70-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a6c70-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a6c70-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6c70-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a6c70-134">See also</span></span>

- [<span data-ttu-id="a6c70-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="a6c70-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
