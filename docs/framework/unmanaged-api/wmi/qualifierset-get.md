---
title: QualifierSet_Get-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_Get-Funktion Ruft einen benannten Qualifizierer ab.
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
ms.openlocfilehash: fd096287b85b4a51a8cae85dddcca95cc1a8dbae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721139"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="6a7a4-103">QualifierSet_Get-Funktion</span><span class="sxs-lookup"><span data-stu-id="6a7a4-103">QualifierSet_Get function</span></span>

<span data-ttu-id="6a7a4-104">Ruft den angegebenen benannten Qualifizierer ab.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6a7a4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a7a4-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="6a7a4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6a7a4-106">Parameters</span></span>

<span data-ttu-id="6a7a4-107">`vFunc` in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="6a7a4-108">`ptr` in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="6a7a4-109">`wszName` in Der Name des Qualifizierers, dessen Wert angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-109">`wszName` [in] The name of the qualifier whose value is requested.</span></span>

<span data-ttu-id="6a7a4-110">`lFlags` in Bleiben.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="6a7a4-111">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-111">This parameter must be 0.</span></span>

<span data-ttu-id="6a7a4-112">`pVal` vorgenommen Bei Erfolg der richtige Typ und Wert für den Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-112">`pVal` [out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="6a7a4-113">Wenn die Funktion fehlschlägt, `VARIANT` wird die, auf die von verwiesen `pVal` wird, nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="6a7a4-114">Wenn dieser Parameter ist `null` , wird der-Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-114">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="6a7a4-115">`plFlavor` vorgenommen Ein Zeiger auf einen Long-Wert, der die qualifizierungsbits für den angeforderten Qualifizierer empfängt.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-115">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="6a7a4-116">Wenn keine Informationen zur Konfiguration erwünscht sind, kann dieser Parameter sein `null` .</span><span class="sxs-lookup"><span data-stu-id="6a7a4-116">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="6a7a4-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6a7a4-117">Return value</span></span>

<span data-ttu-id="6a7a4-118">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="6a7a4-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6a7a4-119">Konstante</span><span class="sxs-lookup"><span data-stu-id="6a7a4-119">Constant</span></span>  |<span data-ttu-id="6a7a4-120">Wert</span><span class="sxs-lookup"><span data-stu-id="6a7a4-120">Value</span></span>  |<span data-ttu-id="6a7a4-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6a7a4-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6a7a4-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6a7a4-122">0x80041008</span></span> | <span data-ttu-id="6a7a4-123">Ein Parameter ist nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="6a7a4-124">0x80041002 angezeigt</span><span class="sxs-lookup"><span data-stu-id="6a7a4-124">0x80041002</span></span> | <span data-ttu-id="6a7a4-125">Der angegebene Qualifizierer ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="6a7a4-126">0</span><span class="sxs-lookup"><span data-stu-id="6a7a4-126">0</span></span> | <span data-ttu-id="6a7a4-127">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="6a7a4-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a7a4-128">Remarks</span></span>

<span data-ttu-id="6a7a4-129">Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) -Methode.</span><span class="sxs-lookup"><span data-stu-id="6a7a4-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="6a7a4-130">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6a7a4-130">Requirements</span></span>  

 <span data-ttu-id="6a7a4-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a7a4-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a7a4-132">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="6a7a4-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6a7a4-133">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6a7a4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a7a4-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a7a4-134">See also</span></span>

- [<span data-ttu-id="6a7a4-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="6a7a4-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
