---
title: QualifierSet_EndEnumeration -Funktion (Nicht verwaltete API-Referenz)
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
ms.openlocfilehash: c606580ff2e02c5659c14b134b1a17a65651952b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176746"
---
# <a name="qualifierset_endenumeration-function"></a><span data-ttu-id="529e7-103">QualifierSet_EndEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="529e7-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="529e7-104">Beendet die Enumeration, die mit einem Aufruf der [QualifierSet_BeginEnumeration-Funktion](qualifierset-beginenumeration.md) begonnen wurde.</span><span class="sxs-lookup"><span data-stu-id="529e7-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="529e7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="529e7-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="529e7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="529e7-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="529e7-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="529e7-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="529e7-108">`ptr`[in] Ein Zeiger auf eine [IWbemQualifierSet-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)</span><span class="sxs-lookup"><span data-stu-id="529e7-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="529e7-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="529e7-109">Return value</span></span>

<span data-ttu-id="529e7-110">Der folgende Wert, der von dieser Funktion zurückgegeben wird, ist in der *PseCli.h-Headerdatei* definiert, oder Sie können ihn als Konstante im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="529e7-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="529e7-111">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="529e7-111">Constant</span></span>  |<span data-ttu-id="529e7-112">value</span><span class="sxs-lookup"><span data-stu-id="529e7-112">Value</span></span>  |<span data-ttu-id="529e7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="529e7-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="529e7-114">0</span><span class="sxs-lookup"><span data-stu-id="529e7-114">0</span></span> | <span data-ttu-id="529e7-115">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="529e7-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="529e7-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="529e7-116">Remarks</span></span>

<span data-ttu-id="529e7-117">Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::EndEnumeration-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration)</span><span class="sxs-lookup"><span data-stu-id="529e7-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="529e7-118">Dieser Aufruf wird empfohlen, ist jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="529e7-118">This call is recommended, but not required.</span></span> <span data-ttu-id="529e7-119">Es gibt sofort Ressourcen frei, die mit der Enumeration verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="529e7-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="529e7-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="529e7-120">Requirements</span></span>  

<span data-ttu-id="529e7-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="529e7-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="529e7-122">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="529e7-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="529e7-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="529e7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="529e7-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="529e7-124">See also</span></span>

- [<span data-ttu-id="529e7-125">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="529e7-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
