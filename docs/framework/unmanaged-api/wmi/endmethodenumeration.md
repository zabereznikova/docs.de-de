---
title: EndMethodEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die EndMethodEnumeration-Funktion wird eine Methode Enumerationsfolge beendet.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: EndMethodEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: EndMethodEnumeration
helpviewer_keywords: EndMethodEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1379adbce449ac3255c359249b0296da96a659a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="fe8b9-103">EndMethodEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="fe8b9-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="fe8b9-104">Beendet eine Enumerationsfolge Schritte mit einem Aufruf der [BeginMethodEnumeration Funktion](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="fe8b9-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="fe8b9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe8b9-105">Syntax</span></span>  
  
```  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="fe8b9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fe8b9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="fe8b9-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe8b9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="fe8b9-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="fe8b9-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="fe8b9-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fe8b9-109">Return value</span></span>

<span data-ttu-id="fe8b9-110">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="fe8b9-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fe8b9-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="fe8b9-111">Constant</span></span>  |<span data-ttu-id="fe8b9-112">Wert</span><span class="sxs-lookup"><span data-stu-id="fe8b9-112">Value</span></span>  |<span data-ttu-id="fe8b9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe8b9-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="fe8b9-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="fe8b9-114">0x8004101d</span></span> | <span data-ttu-id="fe8b9-115">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="fe8b9-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="fe8b9-116">0</span><span class="sxs-lookup"><span data-stu-id="fe8b9-116">0</span></span> | <span data-ttu-id="fe8b9-117">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="fe8b9-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="fe8b9-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fe8b9-118">Remarks</span></span>

<span data-ttu-id="fe8b9-119">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::EndMethodEnumeration](https://msdn.microsoft.com/library/aa391441(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="fe8b9-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](https://msdn.microsoft.com/library/aa391441(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="fe8b9-120">Der Aufrufer startet die Enumeration Sequenz mit [BeginMethodEnumeration-Funktion](beginmethodenumeration.md), und ruft dann die [NextMethod-Funktion](nextmethod.md )bis der Methodenrückgabe `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="fe8b9-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="fe8b9-121">Der Aufrufer beendet die Sequenz optional durch den Aufruf `EndMethodEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="fe8b9-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="fe8b9-122">Der Aufrufer wird möglicherweise beendet, die Enumeration frühzeitig durch Aufrufen von `EndMethodEnumeration` zu einem beliebigen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="fe8b9-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="fe8b9-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fe8b9-123">Requirements</span></span>  
 <span data-ttu-id="fe8b9-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe8b9-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe8b9-125">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fe8b9-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fe8b9-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fe8b9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe8b9-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe8b9-127">See also</span></span>  
[<span data-ttu-id="fe8b9-128">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="fe8b9-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
