---
title: EndMethodEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: EndMethodEnumeration-Funktion beendet wird, eine Methode Enumerationsfolge.
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e7f29c365e9f6ba85f85ceb232f7af89446af2a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213050"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="5d9f4-103">EndMethodEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="5d9f4-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="5d9f4-104">Beendet eine Enumerationsfolge gestartet, die durch einen Aufruf der [BeginMethodEnumeration-Funktion](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="5d9f4-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="5d9f4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d9f4-105">Syntax</span></span>  
  
```  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="5d9f4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d9f4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5d9f4-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d9f4-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5d9f4-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="5d9f4-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="5d9f4-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5d9f4-109">Return value</span></span>

<span data-ttu-id="5d9f4-110">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="5d9f4-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5d9f4-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="5d9f4-111">Constant</span></span>  |<span data-ttu-id="5d9f4-112">Wert</span><span class="sxs-lookup"><span data-stu-id="5d9f4-112">Value</span></span>  |<span data-ttu-id="5d9f4-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d9f4-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="5d9f4-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="5d9f4-114">0x8004101d</span></span> | <span data-ttu-id="5d9f4-115">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="5d9f4-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="5d9f4-116">0</span><span class="sxs-lookup"><span data-stu-id="5d9f4-116">0</span></span> | <span data-ttu-id="5d9f4-117">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="5d9f4-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5d9f4-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d9f4-118">Remarks</span></span>

<span data-ttu-id="5d9f4-119">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) Methode.</span><span class="sxs-lookup"><span data-stu-id="5d9f4-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="5d9f4-120">Der Aufrufer startet die Enumeration Sequenz mit [BeginMethodEnumeration-Funktion](beginmethodenumeration.md), und ruft dann die [NextMethod Funktion](nextmethod.md )bis die Methode zurückgibt `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="5d9f4-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="5d9f4-121">Der Aufrufer wird optional die Sequenz beendet, indem Aufrufen `EndMethodEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="5d9f4-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="5d9f4-122">Der Aufrufer kann die Enumeration beenden, in der frühen durch Aufrufen von `EndMethodEnumeration` zu einem beliebigen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="5d9f4-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d9f4-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d9f4-123">Requirements</span></span>  
 <span data-ttu-id="5d9f4-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d9f4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d9f4-125">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5d9f4-125">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="5d9f4-126">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5d9f4-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5d9f4-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d9f4-127">See also</span></span>

- [<span data-ttu-id="5d9f4-128">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="5d9f4-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
