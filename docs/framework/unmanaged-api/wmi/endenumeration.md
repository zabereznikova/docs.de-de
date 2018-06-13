---
title: "\"EndEnumeration\"-Funktion (Referenz zur nicht verwalteten API)"
description: Die Funktion "EndEnumeration" beendet eine Enumeration.
ms.date: 11/06/2017
api_name:
- EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndEnumeration
helpviewer_keywords:
- EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d77497beb122bef580d6eb142fede33b8cf220e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459517"
---
# <a name="endenumeration-function"></a><span data-ttu-id="62291-103">"EndEnumeration"-Funktion</span><span class="sxs-lookup"><span data-stu-id="62291-103">EndEnumeration function</span></span>
<span data-ttu-id="62291-104">Beendet eine Enumerationsfolge Schritte mit einem Aufruf der [BeginEnumeration Funktion](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="62291-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="62291-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="62291-105">Syntax</span></span>  
  
```  
HRESULT EndEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="62291-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="62291-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="62291-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="62291-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="62291-108">[in] Ein Zeiger auf ein [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Instanz.</span><span class="sxs-lookup"><span data-stu-id="62291-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>


## <a name="return-value"></a><span data-ttu-id="62291-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="62291-109">Return value</span></span>

<span data-ttu-id="62291-110">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="62291-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="62291-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="62291-111">Constant</span></span>  |<span data-ttu-id="62291-112">Wert</span><span class="sxs-lookup"><span data-stu-id="62291-112">Value</span></span>  |<span data-ttu-id="62291-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62291-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="62291-114">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="62291-114">0x80041001</span></span> | <span data-ttu-id="62291-115">Ein allgemeiner Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="62291-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="62291-116">0</span><span class="sxs-lookup"><span data-stu-id="62291-116">0</span></span> | <span data-ttu-id="62291-117">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="62291-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="62291-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62291-118">Remarks</span></span>

<span data-ttu-id="62291-119">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemClassObject::EndEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="62291-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) method.</span></span>

<span data-ttu-id="62291-120">Ein Aufruf der `EndEnumeration` Funktion ist nicht erforderlich, aber es wird empfohlen, da es die Enumeration zugeordnete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="62291-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="62291-121">Allerdings sind die Resoruces automatisch freigegeben, wenn die nächste Aufzählung gestartet wird oder das Objekt freigegeben.</span><span class="sxs-lookup"><span data-stu-id="62291-121">However, the resoruces are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="62291-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62291-122">Requirements</span></span>  
 <span data-ttu-id="62291-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62291-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62291-124">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="62291-124">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="62291-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="62291-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62291-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62291-126">See also</span></span>  
[<span data-ttu-id="62291-127">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="62291-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
