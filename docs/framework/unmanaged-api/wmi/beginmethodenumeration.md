---
title: BeginMethodEnumeration-Funktion (Nicht verwaltete API-Referenz)
description: Die BeginMethodEnumeration-Funktion beginnt mit einer Enumeration der Methoden des Objekts.
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 876f5810fffab7fa98cd4d46715e13569ab95f6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175043"
---
# <a name="beginmethodenumeration-function"></a><span data-ttu-id="e52b0-103">BeginMethodEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="e52b0-103">BeginMethodEnumeration function</span></span>
<span data-ttu-id="e52b0-104">Beginnt eine Aufzählung der für das Objekt verfügbaren Methoden.</span><span class="sxs-lookup"><span data-stu-id="e52b0-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e52b0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e52b0-105">Syntax</span></span>  
  
```cpp
HRESULT BeginMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a><span data-ttu-id="e52b0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e52b0-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e52b0-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e52b0-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e52b0-108">[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="e52b0-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="e52b0-109">[in] Null (0) für alle Methoden oder ein Flag, das den Bereich der Enumeration angibt.</span><span class="sxs-lookup"><span data-stu-id="e52b0-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="e52b0-110">Die folgenden Flags sind in der *PsemCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="e52b0-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="e52b0-111">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="e52b0-111">Constant</span></span>  |<span data-ttu-id="e52b0-112">value</span><span class="sxs-lookup"><span data-stu-id="e52b0-112">Value</span></span>  |<span data-ttu-id="e52b0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e52b0-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="e52b0-114">0x10</span><span class="sxs-lookup"><span data-stu-id="e52b0-114">0x10</span></span> | <span data-ttu-id="e52b0-115">Beschränken Sie die Enumeration auf Methoden, die in der Klasse selbst definiert sind.</span><span class="sxs-lookup"><span data-stu-id="e52b0-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="e52b0-116">0x20</span><span class="sxs-lookup"><span data-stu-id="e52b0-116">0x20</span></span> | <span data-ttu-id="e52b0-117">Beschränken Sie die Enumeration auf Eigenschaften, die von Basisklassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="e52b0-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="e52b0-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e52b0-118">Return value</span></span>

<span data-ttu-id="e52b0-119">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="e52b0-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e52b0-120">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="e52b0-120">Constant</span></span>  |<span data-ttu-id="e52b0-121">value</span><span class="sxs-lookup"><span data-stu-id="e52b0-121">Value</span></span>  |<span data-ttu-id="e52b0-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e52b0-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e52b0-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e52b0-123">0x80041008</span></span> | <span data-ttu-id="e52b0-124">`lEnnumFlags`ist ungleich Null und gehört nicht zu den angegebenen Flags.</span><span class="sxs-lookup"><span data-stu-id="e52b0-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e52b0-125">0</span><span class="sxs-lookup"><span data-stu-id="e52b0-125">0</span></span> | <span data-ttu-id="e52b0-126">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="e52b0-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e52b0-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e52b0-127">Remarks</span></span>

<span data-ttu-id="e52b0-128">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::BeginMethodEnumeration-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration)</span><span class="sxs-lookup"><span data-stu-id="e52b0-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="e52b0-129">Dieser Methodenaufruf wird nur unterstützt, wenn das aktuelle Objekt eine Klassendefinition ist.</span><span class="sxs-lookup"><span data-stu-id="e52b0-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="e52b0-130">Die Methodenmanipulation ist von [IWbemClassObject-Zeigern, die](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) auf Instanzen verweisen, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e52b0-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="e52b0-131">Die Reihenfolge, in der Methoden aufgezählt werden, ist garantiert invariant für eine bestimmte Instanz von [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="e52b0-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="e52b0-132">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e52b0-132">Requirements</span></span>  
 <span data-ttu-id="e52b0-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e52b0-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e52b0-134">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e52b0-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e52b0-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e52b0-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e52b0-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e52b0-136">See also</span></span>

- [<span data-ttu-id="e52b0-137">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="e52b0-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
