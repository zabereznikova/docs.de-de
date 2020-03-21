---
title: QualifierSet_Get -Funktion (Nicht verwaltete API-Referenz)
description: Die QualifierSet_Get-Funktion ruft einen benannten Qualifizierer ab.
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 2f4e2d4518e01f3415b8f17ce5778dd98b2a45c3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174887"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="dd007-103">QualifierSet_Get-Funktion</span><span class="sxs-lookup"><span data-stu-id="dd007-103">QualifierSet_Get function</span></span>
<span data-ttu-id="dd007-104">Ruft den angegebenen benannten Qualifizierer ab.</span><span class="sxs-lookup"><span data-stu-id="dd007-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="dd007-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd007-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a><span data-ttu-id="dd007-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="dd007-106">Parameters</span></span>

<span data-ttu-id="dd007-107">`vFunc`[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="dd007-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="dd007-108">`ptr`[in] Ein Zeiger auf eine [IWbemQualifierSet-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="dd007-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="dd007-109">`wszName`[in] Der Name des Qualifizierers, dessen Wert angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="dd007-109">`wszName` [in] The name of the qualifier whose value is requested.</span></span>

<span data-ttu-id="dd007-110">`lFlags`[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="dd007-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="dd007-111">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="dd007-111">This parameter must be 0.</span></span>

<span data-ttu-id="dd007-112">`pVal`[out] Wenn erfolgreich, der richtige Typ und Wert für den Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="dd007-112">`pVal` [out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="dd007-113">Wenn die Funktion `VARIANT` fehlschlägt, `pVal` wird der spitz auf durch nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="dd007-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="dd007-114">Wenn dieser `null`Parameter ist , wird der Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="dd007-114">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="dd007-115">`plFlavor`[out] Ein Zeiger auf einen LONG, der die Qualifizierer-Geschmackbits für den angeforderten Qualifizierer empfängt.</span><span class="sxs-lookup"><span data-stu-id="dd007-115">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="dd007-116">Wenn Geschmacksinformationen nicht gewünscht werden, kann dieser Parameter . `null`</span><span class="sxs-lookup"><span data-stu-id="dd007-116">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="dd007-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dd007-117">Return value</span></span>

<span data-ttu-id="dd007-118">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="dd007-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="dd007-119">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="dd007-119">Constant</span></span>  |<span data-ttu-id="dd007-120">value</span><span class="sxs-lookup"><span data-stu-id="dd007-120">Value</span></span>  |<span data-ttu-id="dd007-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd007-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="dd007-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="dd007-122">0x80041008</span></span> | <span data-ttu-id="dd007-123">Ein Parameter ist nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="dd007-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="dd007-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="dd007-124">0x80041002</span></span> | <span data-ttu-id="dd007-125">Der angegebene Qualifizierer ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="dd007-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="dd007-126">0</span><span class="sxs-lookup"><span data-stu-id="dd007-126">0</span></span> | <span data-ttu-id="dd007-127">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="dd007-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="dd007-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="dd007-128">Remarks</span></span>

<span data-ttu-id="dd007-129">Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::Get-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get)</span><span class="sxs-lookup"><span data-stu-id="dd007-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="dd007-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dd007-130">Requirements</span></span>  
 <span data-ttu-id="dd007-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd007-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd007-132">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="dd007-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="dd007-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dd007-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd007-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd007-134">See also</span></span>

- [<span data-ttu-id="dd007-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="dd007-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
