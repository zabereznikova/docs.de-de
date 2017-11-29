---
title: BeginMethodEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: "Startet eine Enumeration der Methoden für das Objekt die BeginMethodEnumeration-Funktion"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BeginMethodEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BeginMethodEnumeration
helpviewer_keywords: BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2e44c432f9503f96ad4dab9e25b78e6dd148f94c
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="beginenumeration-function"></a><span data-ttu-id="23894-103">BeginEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="23894-103">BeginEnumeration function</span></span>
<span data-ttu-id="23894-104">Startet eine Enumeration der Methoden für das Objekt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="23894-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="23894-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="23894-105">Syntax</span></span>  
  
``` 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="23894-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="23894-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="23894-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="23894-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="23894-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="23894-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="23894-109">[in] Null (0) für alle Methoden oder ein Flag, das den Bereich der Enumeration angibt.</span><span class="sxs-lookup"><span data-stu-id="23894-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="23894-110">Die folgenden Flags werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="23894-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="23894-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="23894-111">Constant</span></span>  |<span data-ttu-id="23894-112">Wert</span><span class="sxs-lookup"><span data-stu-id="23894-112">Value</span></span>  |<span data-ttu-id="23894-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23894-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="23894-114">0 x 10</span><span class="sxs-lookup"><span data-stu-id="23894-114">0x10</span></span> | <span data-ttu-id="23894-115">Die Enumeration, die in der Klasse selbst definierten Methoden zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="23894-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="23894-116">0 x 20</span><span class="sxs-lookup"><span data-stu-id="23894-116">0x20</span></span> | <span data-ttu-id="23894-117">Begrenzen Sie die Enumeration, die Eigenschaften, die Basis-Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="23894-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="23894-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="23894-118">Return value</span></span>

<span data-ttu-id="23894-119">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="23894-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="23894-120">Konstante</span><span class="sxs-lookup"><span data-stu-id="23894-120">Constant</span></span>  |<span data-ttu-id="23894-121">Wert</span><span class="sxs-lookup"><span data-stu-id="23894-121">Value</span></span>  |<span data-ttu-id="23894-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23894-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="23894-123">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="23894-123">0x80041008</span></span> | <span data-ttu-id="23894-124">`lEnnumFlags`ist ungleich NULL und ist nicht der angegebenen Flags.</span><span class="sxs-lookup"><span data-stu-id="23894-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="23894-125">0</span><span class="sxs-lookup"><span data-stu-id="23894-125">0</span></span> | <span data-ttu-id="23894-126">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="23894-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="23894-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23894-127">Remarks</span></span>

<span data-ttu-id="23894-128">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::BeginMethodEnumeration](https://msdn.microsoft.com/library/aa391435(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="23894-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](https://msdn.microsoft.com/library/aa391435(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="23894-129">Dieser Methodenaufruf wird nur unterstützt, wenn das aktuelle Objekt einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="23894-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="23894-130">Methode Manipulation steht nicht zur Verfügung [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Zeiger, die auf Instanzen verweisen.</span><span class="sxs-lookup"><span data-stu-id="23894-130">Method manipulation is not available from [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointers that point to instances.</span></span> <span data-ttu-id="23894-131">Die Reihenfolge, in dem Methoden werden aufgezählt, ist garantiert für eine bestimmte Instanz des invariant [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="23894-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx).</span></span>

## <a name="requirements"></a><span data-ttu-id="23894-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23894-132">Requirements</span></span>  
 <span data-ttu-id="23894-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23894-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23894-134">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="23894-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="23894-135">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="23894-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23894-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23894-136">See also</span></span>  
[<span data-ttu-id="23894-137">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="23894-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
