---
title: Getmethodorigin-Funktion (Referenz zur nicht verwalteten API)
description: Die getmethodorigin-Funktion bestimmt die Klasse, in der eine Methode deklariert wird.
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
ms.openlocfilehash: 434392ffb4d9124e319bcd9c42fdd340d3fec5b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722777"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="a109e-103">GetMethodOrigin-Funktion</span><span class="sxs-lookup"><span data-stu-id="a109e-103">GetMethodOrigin function</span></span>

<span data-ttu-id="a109e-104">Bestimmt die Klasse, in der eine Methode deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="a109e-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="a109e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a109e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```  

## <a name="parameters"></a><span data-ttu-id="a109e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a109e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="a109e-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a109e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="a109e-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="a109e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="a109e-109">in Der Name der Methode für das Objekt, dessen besitzende Klasse angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="a109e-109">[in] The name of the method for the object whose owning class is being requested.</span></span>

`pstrClassName`  
<span data-ttu-id="a109e-110">vorgenommen Empfängt den Namen der Klasse, die die Methode besitzt.</span><span class="sxs-lookup"><span data-stu-id="a109e-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="a109e-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a109e-111">Return value</span></span>

<span data-ttu-id="a109e-112">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="a109e-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a109e-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="a109e-113">Constant</span></span>  |<span data-ttu-id="a109e-114">Wert</span><span class="sxs-lookup"><span data-stu-id="a109e-114">Value</span></span>  |<span data-ttu-id="a109e-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a109e-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="a109e-116">0x80041002 angezeigt</span><span class="sxs-lookup"><span data-stu-id="a109e-116">0x80041002</span></span> | <span data-ttu-id="a109e-117">Die angegebene Methode wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="a109e-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a109e-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a109e-118">0x80041008</span></span> | <span data-ttu-id="a109e-119">Mindestens ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="a109e-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a109e-120">0</span><span class="sxs-lookup"><span data-stu-id="a109e-120">0</span></span> | <span data-ttu-id="a109e-121">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="a109e-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="a109e-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a109e-122">Remarks</span></span>

<span data-ttu-id="a109e-123">Diese Funktion umschließt einen Aufruf der [IWbemClassObject:: getmethodorigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) -Methode.</span><span class="sxs-lookup"><span data-stu-id="a109e-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="a109e-124">Da eine Klasse Methoden von einer oder mehreren Basisklassen erben kann, möchten Entwickler häufig die Klasse bestimmen, in der eine bestimmte Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="a109e-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="a109e-125">Der- `pstrClassName` Parameter darf nicht auf einen gültigen verweisen, `BSTR` bevor die-Funktion aufgerufen wird, da es sich hierbei um einen `out` Parameter handelt. dieser Zeiger wird nicht aufgehoben, nachdem die Funktion zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a109e-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="a109e-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a109e-126">Requirements</span></span>  

<span data-ttu-id="a109e-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a109e-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a109e-128">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="a109e-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a109e-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a109e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a109e-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a109e-130">See also</span></span>

- [<span data-ttu-id="a109e-131">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="a109e-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
