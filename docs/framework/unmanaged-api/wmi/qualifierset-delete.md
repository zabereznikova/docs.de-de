---
title: QualifierSet_Delete -Funktion (Nicht verwaltete API-Referenz)
description: Die QualifierSet_Delete-Funktion löscht einen Qualifizierer nach Namen.
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
ms.openlocfilehash: 0d2a02ba9d89ba16e776bb73563eaebf8a92f1fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174900"
---
# <a name="qualifierset_delete-function"></a><span data-ttu-id="da033-103">QualifierSet_Delete-Funktion</span><span class="sxs-lookup"><span data-stu-id="da033-103">QualifierSet_Delete function</span></span>
<span data-ttu-id="da033-104">Löscht einen angegebenen Qualifizierer anhand des Namens.</span><span class="sxs-lookup"><span data-stu-id="da033-104">Deletes a specified qualifier by name.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="da033-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="da033-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName
);
```  

## <a name="parameters"></a><span data-ttu-id="da033-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="da033-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="da033-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="da033-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="da033-108">`ptr`[in] Ein Zeiger auf eine [IWbemQualifierSet-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="da033-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="da033-109">`wszName`[in] Der Name des zu löschenden Qualifizierers.</span><span class="sxs-lookup"><span data-stu-id="da033-109">`wszName` [in] The name of the qualifier to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="da033-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="da033-110">Return value</span></span>

<span data-ttu-id="da033-111">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="da033-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="da033-112">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="da033-112">Constant</span></span>  |<span data-ttu-id="da033-113">value</span><span class="sxs-lookup"><span data-stu-id="da033-113">Value</span></span>  |<span data-ttu-id="da033-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da033-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="da033-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="da033-115">0x80041008</span></span> | <span data-ttu-id="da033-116">Der `wszName`-Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="da033-116">The `wszName` parameter is not valid.</span></span> |
|`WBEM_E_INVALID_OPERATION` | <span data-ttu-id="da033-117">0x80041016</span><span class="sxs-lookup"><span data-stu-id="da033-117">0x80041016</span></span> | <span data-ttu-id="da033-118">Das Löschen dieses Qualifizierers ist unzulässig.</span><span class="sxs-lookup"><span data-stu-id="da033-118">Deleting this qualifier is illegal.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="da033-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="da033-119">0x80041002</span></span> | <span data-ttu-id="da033-120">Der angegebene Qualifizierer wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="da033-120">The specified qualifier was not found.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="da033-121">0</span><span class="sxs-lookup"><span data-stu-id="da033-121">0</span></span> | <span data-ttu-id="da033-122">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="da033-122">The function call was successful.</span></span>  |
| `WBEM_S_RESET_TO_DEFAULT` | <span data-ttu-id="da033-123">0x40002</span><span class="sxs-lookup"><span data-stu-id="da033-123">0x40002</span></span> | <span data-ttu-id="da033-124">Die lokale Außerkraftsetzung wurde gelöscht, und der ursprüngliche Qualifizierer aus dem übergeordneten Objekt hat den Gültigkeitsbereich wieder aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="da033-124">The local override was deleted and the original qualifier from the parent object has resumed scope.</span></span> |

## <a name="remarks"></a><span data-ttu-id="da033-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="da033-125">Remarks</span></span>

<span data-ttu-id="da033-126">Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::Delete-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete)</span><span class="sxs-lookup"><span data-stu-id="da033-126">This function wraps a call to the [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) method.</span></span>

<span data-ttu-id="da033-127">Aufgrund von Qualifizierer-Weitergaberegeln wurde ein bestimmter Qualifizierer möglicherweise von einem anderen Objekt geerbt und lediglich in der aktuellen Klasse oder Instanz überschrieben.</span><span class="sxs-lookup"><span data-stu-id="da033-127">Due to qualifier propagation rules, a particular qualifier may have been inherited from another object and merely overridden in the current class or instance.</span></span> <span data-ttu-id="da033-128">In diesem Fall `QualifierSet_Delete` setzt die Methode den Qualifizierer auf den ursprünglichen geerbten Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="da033-128">In this case, the `QualifierSet_Delete` method resets the qualifier to its original inherited value.</span></span> <span data-ttu-id="da033-129">Die Funktion gibt in diesem `WBEM_S_RESET_TO_DEFAULT`Fall den Statuscode zurück.</span><span class="sxs-lookup"><span data-stu-id="da033-129">The function in this case returns the status code `WBEM_S_RESET_TO_DEFAULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="da033-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="da033-130">Requirements</span></span>  
 <span data-ttu-id="da033-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da033-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da033-132">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="da033-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="da033-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="da033-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da033-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da033-134">See also</span></span>

- [<span data-ttu-id="da033-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="da033-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
