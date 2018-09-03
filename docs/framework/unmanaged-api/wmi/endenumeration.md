---
title: EndEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion "EndEnumeration" wird eine Enumeration beendet.
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
ms.openlocfilehash: 33c73e58be39a7f1ffa9300947c3ee552231adab
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43462310"
---
# <a name="endenumeration-function"></a><span data-ttu-id="568c7-103">EndEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="568c7-103">EndEnumeration function</span></span>
<span data-ttu-id="568c7-104">Beendet eine Enumerationsfolge gestartet, die durch einen Aufruf der [BeginEnumeration-Funktion](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="568c7-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="568c7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="568c7-105">Syntax</span></span>  
  
```  
HRESULT EndEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="568c7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="568c7-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="568c7-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="568c7-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="568c7-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="568c7-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>


## <a name="return-value"></a><span data-ttu-id="568c7-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="568c7-109">Return value</span></span>

<span data-ttu-id="568c7-110">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="568c7-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="568c7-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="568c7-111">Constant</span></span>  |<span data-ttu-id="568c7-112">Wert</span><span class="sxs-lookup"><span data-stu-id="568c7-112">Value</span></span>  |<span data-ttu-id="568c7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="568c7-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="568c7-114">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="568c7-114">0x80041001</span></span> | <span data-ttu-id="568c7-115">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="568c7-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="568c7-116">0</span><span class="sxs-lookup"><span data-stu-id="568c7-116">0</span></span> | <span data-ttu-id="568c7-117">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="568c7-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="568c7-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="568c7-118">Remarks</span></span>

<span data-ttu-id="568c7-119">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Methode.</span><span class="sxs-lookup"><span data-stu-id="568c7-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="568c7-120">Ein Aufruf der `EndEnumeration` Funktion ist nicht erforderlich, aber es wird empfohlen, da es die Enumeration zugeordnete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="568c7-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="568c7-121">Allerdings werden die Ressourcen automatisch freigegeben, wenn die nächste Aufzählung gestartet wird oder das Objekt freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="568c7-121">However, the resoruces are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="568c7-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="568c7-122">Requirements</span></span>  
 <span data-ttu-id="568c7-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="568c7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="568c7-124">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="568c7-124">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="568c7-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="568c7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="568c7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="568c7-126">See also</span></span>  
[<span data-ttu-id="568c7-127">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="568c7-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
