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
ms.openlocfilehash: dc09cd30c43647fa00cccc1dc00da4f8de367e84
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127277"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="8794f-103">QualifierSet_Get-Funktion</span><span class="sxs-lookup"><span data-stu-id="8794f-103">QualifierSet_Get function</span></span>
<span data-ttu-id="8794f-104">Ruft den angegebenen benannten Qualifizierer ab.</span><span class="sxs-lookup"><span data-stu-id="8794f-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8794f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8794f-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="8794f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8794f-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="8794f-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="8794f-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="8794f-108">in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="8794f-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="8794f-109">in Der Name des Qualifizierers, dessen Wert angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="8794f-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="8794f-110">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="8794f-110">[in] Reserved.</span></span> <span data-ttu-id="8794f-111">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="8794f-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="8794f-112">vorgenommen Bei Erfolg der richtige Typ und Wert für den Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="8794f-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="8794f-113">Wenn die Funktion fehlschlägt, wird die `VARIANT`, auf die `pVal` verweist, nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="8794f-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="8794f-114">Wenn dieser Parameter `null`ist, wird der-Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8794f-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="8794f-115">vorgenommen Ein Zeiger auf einen Long-Wert, der die qualifizierungsbits für den angeforderten Qualifizierer empfängt.</span><span class="sxs-lookup"><span data-stu-id="8794f-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="8794f-116">Wenn keine Informationen zur Konfiguration erwünscht sind, kann dieser Parameter `null`werden.</span><span class="sxs-lookup"><span data-stu-id="8794f-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="8794f-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8794f-117">Return value</span></span>

<span data-ttu-id="8794f-118">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="8794f-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8794f-119">Konstante</span><span class="sxs-lookup"><span data-stu-id="8794f-119">Constant</span></span>  |<span data-ttu-id="8794f-120">Wert</span><span class="sxs-lookup"><span data-stu-id="8794f-120">Value</span></span>  |<span data-ttu-id="8794f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8794f-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8794f-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8794f-122">0x80041008</span></span> | <span data-ttu-id="8794f-123">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8794f-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="8794f-124">0x80041002 angezeigt</span><span class="sxs-lookup"><span data-stu-id="8794f-124">0x80041002</span></span> | <span data-ttu-id="8794f-125">Der angegebene Qualifizierer ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="8794f-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8794f-126">0</span><span class="sxs-lookup"><span data-stu-id="8794f-126">0</span></span> | <span data-ttu-id="8794f-127">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8794f-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8794f-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8794f-128">Remarks</span></span>

<span data-ttu-id="8794f-129">Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) -Methode.</span><span class="sxs-lookup"><span data-stu-id="8794f-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8794f-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8794f-130">Requirements</span></span>  
 <span data-ttu-id="8794f-131">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8794f-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8794f-132">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="8794f-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8794f-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8794f-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8794f-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8794f-134">See also</span></span>

- [<span data-ttu-id="8794f-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="8794f-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
