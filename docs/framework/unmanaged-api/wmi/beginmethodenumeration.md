---
title: Beginmethodenumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die beginmethodenumeration-Funktion beginnt eine Enumeration der Methoden des Objekts.
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
ms.openlocfilehash: be1e86e0b760ab403cf42ac19da03f84769a85cf
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884422"
---
# <a name="beginmethodenumeration-function"></a><span data-ttu-id="685ac-103">BeginMethodEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="685ac-103">BeginMethodEnumeration function</span></span>
<span data-ttu-id="685ac-104">Beginnt eine Enumeration der Methoden, die für das-Objekt verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="685ac-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="685ac-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="685ac-105">Syntax</span></span>  
  
```cpp 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="685ac-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="685ac-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="685ac-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="685ac-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="685ac-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="685ac-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="685ac-109">in NULL (0) für alle Methoden oder ein Flag, das den Bereich der Enumeration angibt.</span><span class="sxs-lookup"><span data-stu-id="685ac-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="685ac-110">Die folgenden Flags sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="685ac-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="685ac-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="685ac-111">Constant</span></span>  |<span data-ttu-id="685ac-112">{2&gt;Wert&lt;2}</span><span class="sxs-lookup"><span data-stu-id="685ac-112">Value</span></span>  |<span data-ttu-id="685ac-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="685ac-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="685ac-114">0x10</span><span class="sxs-lookup"><span data-stu-id="685ac-114">0x10</span></span> | <span data-ttu-id="685ac-115">Beschränken Sie die Enumeration auf Methoden, die in der Klasse selbst definiert sind.</span><span class="sxs-lookup"><span data-stu-id="685ac-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="685ac-116">0x20</span><span class="sxs-lookup"><span data-stu-id="685ac-116">0x20</span></span> | <span data-ttu-id="685ac-117">Beschränken Sie die Enumeration auf Eigenschaften, die von Basisklassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="685ac-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="685ac-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="685ac-118">Return value</span></span>

<span data-ttu-id="685ac-119">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="685ac-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="685ac-120">Konstante</span><span class="sxs-lookup"><span data-stu-id="685ac-120">Constant</span></span>  |<span data-ttu-id="685ac-121">{2&gt;Wert&lt;2}</span><span class="sxs-lookup"><span data-stu-id="685ac-121">Value</span></span>  |<span data-ttu-id="685ac-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="685ac-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="685ac-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="685ac-123">0x80041008</span></span> | <span data-ttu-id="685ac-124">`lEnnumFlags` ist ungleich 0 (null) und ist nicht eines der angegebenen Flags.</span><span class="sxs-lookup"><span data-stu-id="685ac-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="685ac-125">0</span><span class="sxs-lookup"><span data-stu-id="685ac-125">0</span></span> | <span data-ttu-id="685ac-126">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="685ac-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="685ac-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="685ac-127">Remarks</span></span>

<span data-ttu-id="685ac-128">Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: beginmethodenumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) -Methode.</span><span class="sxs-lookup"><span data-stu-id="685ac-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="685ac-129">Dieser Methoden Aufrufwert wird nur unterstützt, wenn das aktuelle-Objekt eine Klassendefinition ist.</span><span class="sxs-lookup"><span data-stu-id="685ac-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="685ac-130">Die Methoden Bearbeitung ist nicht in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Zeigern verfügbar, die auf-Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="685ac-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="685ac-131">Die Reihenfolge, in der Methoden aufgelistet werden, ist für eine bestimmte Instanz von [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)garantiert invariante.</span><span class="sxs-lookup"><span data-stu-id="685ac-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="685ac-132">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="685ac-132">Requirements</span></span>  
 <span data-ttu-id="685ac-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="685ac-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="685ac-134">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="685ac-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="685ac-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="685ac-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685ac-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="685ac-136">See also</span></span>

- [<span data-ttu-id="685ac-137">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="685ac-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
