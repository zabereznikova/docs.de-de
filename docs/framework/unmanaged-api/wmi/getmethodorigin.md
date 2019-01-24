---
title: GetMethodOrigin-Funktion (Referenz zur nicht verwalteten API)
description: GetMethodOrigin-Funktion bestimmt die Klasse, die in der eine Methode deklariert ist.
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76f449e52168001a2aaac6cbc3707361cf7f809a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582463"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="fabbf-103">GetMethodOrigin-Funktion</span><span class="sxs-lookup"><span data-stu-id="fabbf-103">GetMethodOrigin function</span></span>
<span data-ttu-id="fabbf-104">Bestimmt die Klasse, in der eine Methode deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="fabbf-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="fabbf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fabbf-105">Syntax</span></span>  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="fabbf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fabbf-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="fabbf-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="fabbf-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="fabbf-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="fabbf-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="fabbf-109">[in] Der Name der Methode für das Objekt, dessen übergeordnete Klasse angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="fabbf-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="fabbf-110">[out] Erhält den Namen der Klasse, die die Methode besitzt.</span><span class="sxs-lookup"><span data-stu-id="fabbf-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="fabbf-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fabbf-111">Return value</span></span>

<span data-ttu-id="fabbf-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="fabbf-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fabbf-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="fabbf-113">Constant</span></span>  |<span data-ttu-id="fabbf-114">Wert</span><span class="sxs-lookup"><span data-stu-id="fabbf-114">Value</span></span>  |<span data-ttu-id="fabbf-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fabbf-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="fabbf-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="fabbf-116">0x80041002</span></span> | <span data-ttu-id="fabbf-117">Die angegebene Methode wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="fabbf-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fabbf-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fabbf-118">0x80041008</span></span> | <span data-ttu-id="fabbf-119">Ein oder mehrere Parameter sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="fabbf-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="fabbf-120">0</span><span class="sxs-lookup"><span data-stu-id="fabbf-120">0</span></span> | <span data-ttu-id="fabbf-121">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="fabbf-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="fabbf-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fabbf-122">Remarks</span></span>

<span data-ttu-id="fabbf-123">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) Methode.</span><span class="sxs-lookup"><span data-stu-id="fabbf-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="fabbf-124">Da eine Klasse Methoden aus einem oder mehreren Basisklassen erben kann, möchten Entwickler häufig die Klasse zu ermitteln, in der eine bestimmte Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fabbf-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="fabbf-125">Die `pstrClassName` Parameter muss nicht auf einen gültigen zeigen `BSTR` , bevor die Funktion aufgerufen wird, da es sich handelt ein `out` Parameter; diese Zeiger wird nicht aufgehoben werden, nachdem die Funktion.</span><span class="sxs-lookup"><span data-stu-id="fabbf-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="fabbf-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fabbf-126">Requirements</span></span>  
<span data-ttu-id="fabbf-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fabbf-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fabbf-128">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fabbf-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fabbf-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fabbf-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fabbf-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fabbf-130">See also</span></span>
- [<span data-ttu-id="fabbf-131">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="fabbf-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
