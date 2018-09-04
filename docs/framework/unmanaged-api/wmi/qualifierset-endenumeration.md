---
title: QualifierSet_EndEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_EndEnumeration-Funktion wird eine Enumeration beendet.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dbf47dbfddac7d48b78c9d52969de1ef03385c15
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524313"
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="51abb-103">QualifierSet_EndEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="51abb-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="51abb-104">Beendet die Enumeration, die mit einem Aufruf gestartet wurde die [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="51abb-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="51abb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="51abb-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="51abb-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="51abb-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="51abb-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="51abb-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="51abb-108">[in] Ein Zeiger auf ein [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) Instanz.</span><span class="sxs-lookup"><span data-stu-id="51abb-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="51abb-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="51abb-109">Return value</span></span>

<span data-ttu-id="51abb-110">Der folgende Wert zurückgegeben, die von dieser Funktion wird definiert, der *WbemCli.h* Header-Datei, oder Sie können ihn definieren als Konstante in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="51abb-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="51abb-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="51abb-111">Constant</span></span>  |<span data-ttu-id="51abb-112">Wert</span><span class="sxs-lookup"><span data-stu-id="51abb-112">Value</span></span>  |<span data-ttu-id="51abb-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51abb-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="51abb-114">0</span><span class="sxs-lookup"><span data-stu-id="51abb-114">0</span></span> | <span data-ttu-id="51abb-115">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="51abb-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="51abb-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51abb-116">Remarks</span></span>

<span data-ttu-id="51abb-117">Diese Funktion umschließt einen Aufruf der [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) Methode.</span><span class="sxs-lookup"><span data-stu-id="51abb-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) method.</span></span>

<span data-ttu-id="51abb-118">Dieser Aufruf wird empfohlen, aber nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="51abb-118">This call is recommended, but not required.</span></span> <span data-ttu-id="51abb-119">Es gibt sofort die Enumeration zugeordnete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="51abb-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="51abb-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51abb-120">Requirements</span></span>  

<span data-ttu-id="51abb-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51abb-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="51abb-122">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="51abb-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="51abb-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="51abb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51abb-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51abb-124">See also</span></span>  
[<span data-ttu-id="51abb-125">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="51abb-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
