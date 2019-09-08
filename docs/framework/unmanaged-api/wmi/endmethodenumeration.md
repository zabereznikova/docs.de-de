---
title: Endmethodenumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die endmethodenumeration-Funktion beendet eine enumerationssequenz der Methode.
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
ms.openlocfilehash: cdcf49bd748a423b1cebfba88644aa961f1c7b65
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799344"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="d6505-103">EndMethodEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="d6505-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="d6505-104">Beendet eine enumerationssequenz, die mit einem Aufrufen der [beginmethodenumeration-Funktion](beginmethodenumeration.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="d6505-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="d6505-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6505-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="d6505-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6505-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="d6505-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6505-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="d6505-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="d6505-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="d6505-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d6505-109">Return value</span></span>

<span data-ttu-id="d6505-110">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="d6505-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d6505-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="d6505-111">Constant</span></span>  |<span data-ttu-id="d6505-112">Wert</span><span class="sxs-lookup"><span data-stu-id="d6505-112">Value</span></span>  |<span data-ttu-id="d6505-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6505-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="d6505-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="d6505-114">0x8004101d</span></span> | <span data-ttu-id="d6505-115">Interner Fehler.</span><span class="sxs-lookup"><span data-stu-id="d6505-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d6505-116">0</span><span class="sxs-lookup"><span data-stu-id="d6505-116">0</span></span> | <span data-ttu-id="d6505-117">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d6505-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="d6505-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6505-118">Remarks</span></span>

<span data-ttu-id="d6505-119">Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: endmethodenumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) -Methode.</span><span class="sxs-lookup"><span data-stu-id="d6505-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="d6505-120">Der Aufrufer startet die enumerationssequenz mithilfe der [beginmethodenumeration-Funktion](beginmethodenumeration.md)und ruft dann die [nextmethod](nextmethod.md )- `WBEM_S_NO_MORE_DATA`Funktion auf, bis die Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d6505-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="d6505-121">Der Aufrufer schließt die Sequenz optional `EndMethodEnumeration`durch Aufrufen von ab.</span><span class="sxs-lookup"><span data-stu-id="d6505-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="d6505-122">Der Aufrufer kann die Enumeration frühzeitig `EndMethodEnumeration` beenden, indem er jederzeit aufruft.</span><span class="sxs-lookup"><span data-stu-id="d6505-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="d6505-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d6505-123">Requirements</span></span>  
 <span data-ttu-id="d6505-124">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6505-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6505-125">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d6505-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="d6505-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d6505-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6505-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6505-127">See also</span></span>

- [<span data-ttu-id="d6505-128">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="d6505-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
