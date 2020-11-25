---
title: QualifierSet_EndEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_EndEnumeration-Funktion beendet eine Enumeration.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 2739003fc9c1f93d379e4a59338cbef7a1a0f135
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726742"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="9798e-103">QualifierSet_EndEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="9798e-103">QualifierSet_EndEnumeration function</span></span>

<span data-ttu-id="9798e-104">Beendet die Enumeration, die mit einem aufzurufenden [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) Funktion gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="9798e-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="9798e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9798e-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="9798e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9798e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="9798e-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9798e-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="9798e-108">`ptr` in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="9798e-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="9798e-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9798e-109">Return value</span></span>

<span data-ttu-id="9798e-110">Der folgende Wert, der von dieser Funktion zurückgegeben wird, ist in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstante im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="9798e-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="9798e-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="9798e-111">Constant</span></span>  |<span data-ttu-id="9798e-112">Wert</span><span class="sxs-lookup"><span data-stu-id="9798e-112">Value</span></span>  |<span data-ttu-id="9798e-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9798e-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="9798e-114">0</span><span class="sxs-lookup"><span data-stu-id="9798e-114">0</span></span> | <span data-ttu-id="9798e-115">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="9798e-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="9798e-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9798e-116">Remarks</span></span>

<span data-ttu-id="9798e-117">Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset:: EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) -Methode.</span><span class="sxs-lookup"><span data-stu-id="9798e-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="9798e-118">Dieser Befehl wird empfohlen, ist jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9798e-118">This call is recommended, but not required.</span></span> <span data-ttu-id="9798e-119">Es werden sofort die der-Enumeration zugeordneten Ressourcen freigegeben.</span><span class="sxs-lookup"><span data-stu-id="9798e-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="9798e-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9798e-120">Requirements</span></span>  

<span data-ttu-id="9798e-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9798e-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="9798e-122">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="9798e-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="9798e-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9798e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9798e-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9798e-124">See also</span></span>

- [<span data-ttu-id="9798e-125">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="9798e-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
