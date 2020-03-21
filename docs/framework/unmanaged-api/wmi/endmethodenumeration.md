---
title: EndMethodEnumeration-Funktion (Nicht verwaltete API-Referenz)
description: Die EndMethodEnumeration-Funktion beendet eine Methodenenumerationssequenz.
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
ms.openlocfilehash: 63667d0668f905ded2aedd961be0d1831faf838c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175004"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="f6b64-103">EndMethodEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="f6b64-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="f6b64-104">Beendet eine Enumerationssequenz, die mit einem Aufruf der [BeginMethodEnumeration-Funktion](beginmethodenumeration.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f6b64-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="f6b64-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6b64-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="f6b64-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6b64-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f6b64-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6b64-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f6b64-108">[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="f6b64-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="f6b64-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f6b64-109">Return value</span></span>

<span data-ttu-id="f6b64-110">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="f6b64-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f6b64-111">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="f6b64-111">Constant</span></span>  |<span data-ttu-id="f6b64-112">value</span><span class="sxs-lookup"><span data-stu-id="f6b64-112">Value</span></span>  |<span data-ttu-id="f6b64-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6b64-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="f6b64-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="f6b64-114">0x8004101d</span></span> | <span data-ttu-id="f6b64-115">Ein interner Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f6b64-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f6b64-116">0</span><span class="sxs-lookup"><span data-stu-id="f6b64-116">0</span></span> | <span data-ttu-id="f6b64-117">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="f6b64-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f6b64-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f6b64-118">Remarks</span></span>

<span data-ttu-id="f6b64-119">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::EndMethodEnumeration-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration)</span><span class="sxs-lookup"><span data-stu-id="f6b64-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="f6b64-120">Der Aufrufer beginnt die Enumerationssequenz mit der [BeginMethodEnumeration-Funktion](beginmethodenumeration.md)und `WBEM_S_NO_MORE_DATA`ruft dann die [NextMethod-Funktion](nextmethod.md )auf, bis die Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f6b64-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="f6b64-121">Der Aufrufer beendet die Sequenz `EndMethodEnumeration`optional, indem er aufruft.</span><span class="sxs-lookup"><span data-stu-id="f6b64-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="f6b64-122">Der Aufrufer kann die Enumeration `EndMethodEnumeration` jederzeit vorzeitig beenden.</span><span class="sxs-lookup"><span data-stu-id="f6b64-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="f6b64-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f6b64-123">Requirements</span></span>  
 <span data-ttu-id="f6b64-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6b64-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6b64-125">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f6b64-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f6b64-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f6b64-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b64-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f6b64-127">See also</span></span>

- [<span data-ttu-id="f6b64-128">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="f6b64-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
