---
title: BeginMethodEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Startet eine Enumeration von Methoden des Objekts die BeginMethodEnumeration-Funktion
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b682904a8e7f2eafa8833d784febe7b3b2a1e5f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611084"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="0e1b2-103">BeginEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="0e1b2-103">BeginEnumeration function</span></span>
<span data-ttu-id="0e1b2-104">Startet eine Enumeration der verfügbaren Methoden für das Objekt.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="0e1b2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e1b2-105">Syntax</span></span>  
  
``` 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="0e1b2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0e1b2-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0e1b2-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0e1b2-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="0e1b2-109">[in] 0 (null) für alle Methoden oder ein Flag, das den Bereich der Enumeration angibt.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="0e1b2-110">Die folgenden Flags werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="0e1b2-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="0e1b2-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="0e1b2-111">Constant</span></span>  |<span data-ttu-id="0e1b2-112">Wert</span><span class="sxs-lookup"><span data-stu-id="0e1b2-112">Value</span></span>  |<span data-ttu-id="0e1b2-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e1b2-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="0e1b2-114">0x10</span><span class="sxs-lookup"><span data-stu-id="0e1b2-114">0x10</span></span> | <span data-ttu-id="0e1b2-115">Beschränken Sie die Enumeration, die Methoden, die in der Klasse selbst definiert werden.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="0e1b2-116">0x20</span><span class="sxs-lookup"><span data-stu-id="0e1b2-116">0x20</span></span> | <span data-ttu-id="0e1b2-117">Beschränken Sie die Enumeration auf Eigenschaften, die von Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="0e1b2-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0e1b2-118">Return value</span></span>

<span data-ttu-id="0e1b2-119">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="0e1b2-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0e1b2-120">Konstante</span><span class="sxs-lookup"><span data-stu-id="0e1b2-120">Constant</span></span>  |<span data-ttu-id="0e1b2-121">Wert</span><span class="sxs-lookup"><span data-stu-id="0e1b2-121">Value</span></span>  |<span data-ttu-id="0e1b2-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e1b2-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0e1b2-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0e1b2-123">0x80041008</span></span> | <span data-ttu-id="0e1b2-124">`lEnnumFlags` ist ungleich NULL und ist keiner der angegebenen Flags.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0e1b2-125">0</span><span class="sxs-lookup"><span data-stu-id="0e1b2-125">0</span></span> | <span data-ttu-id="0e1b2-126">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0e1b2-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e1b2-127">Remarks</span></span>

<span data-ttu-id="0e1b2-128">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) Methode.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="0e1b2-129">Dieser Methodenaufruf wird nur unterstützt, wenn das aktuelle Objekt einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="0e1b2-130">Bearbeitung der Methode ist nicht verfügbar [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Zeigern, die auf Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="0e1b2-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="0e1b2-131">Die Reihenfolge, in dem werden Methoden aufgelistet, ist garantiert für eine bestimmte Instanz von invarianten [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="0e1b2-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="0e1b2-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e1b2-132">Requirements</span></span>  
 <span data-ttu-id="0e1b2-133">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e1b2-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e1b2-134">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0e1b2-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0e1b2-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0e1b2-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e1b2-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e1b2-136">See also</span></span>
- [<span data-ttu-id="0e1b2-137">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="0e1b2-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
