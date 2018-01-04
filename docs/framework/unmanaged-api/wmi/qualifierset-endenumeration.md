---
title: QualifierSet_EndEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion QualifierSet_EndEnumeration beendet eine Enumeration.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_EndEnumeration
helpviewer_keywords: QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d8e6bb24eb471d807af2493f82b6be4f644124f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="bb99f-103">QualifierSet_EndEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="bb99f-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="bb99f-104">Beendet die Enumeration, die mit einem Aufruf von begonnen der [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="bb99f-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bb99f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb99f-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="bb99f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb99f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="bb99f-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb99f-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="bb99f-108">[in] Ein Zeiger auf ein [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="bb99f-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="bb99f-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bb99f-109">Return value</span></span>

<span data-ttu-id="bb99f-110">Der folgende Wert, der von dieser Funktion zurückgegebenen wird definiert, der *WbemCli.h* Header-Datei, oder Sie können es als definieren eine Konstante in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="bb99f-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="bb99f-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="bb99f-111">Constant</span></span>  |<span data-ttu-id="bb99f-112">Wert</span><span class="sxs-lookup"><span data-stu-id="bb99f-112">Value</span></span>  |<span data-ttu-id="bb99f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb99f-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="bb99f-114">0</span><span class="sxs-lookup"><span data-stu-id="bb99f-114">0</span></span> | <span data-ttu-id="bb99f-115">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="bb99f-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="bb99f-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb99f-116">Remarks</span></span>

<span data-ttu-id="bb99f-117">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="bb99f-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="bb99f-118">Dieser Aufruf wird empfohlen, jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bb99f-118">This call is recommended, but not required.</span></span> <span data-ttu-id="bb99f-119">Es gibt sofort die Enumeration zugeordnete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="bb99f-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb99f-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb99f-120">Requirements</span></span>  

<span data-ttu-id="bb99f-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb99f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="bb99f-122">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bb99f-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="bb99f-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bb99f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb99f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb99f-124">See also</span></span>  
[<span data-ttu-id="bb99f-125">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="bb99f-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
