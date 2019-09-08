---
title: Getpropertyorigin-Funktion (Referenz zur nicht verwalteten API)
description: Die getpropertyorigin-Funktion bestimmt die Klasse, in der eine Eigenschaft deklariert wird.
ms.date: 11/06/2017
api_name:
- GetPropertyOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyOrigin
helpviewer_keywords:
- GetPropertyOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c2d0f23f3dd2d52f73f09c32d4e3118a9ed5ea3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798495"
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="6ea92-103">GetPropertyOrigin-Funktion</span><span class="sxs-lookup"><span data-stu-id="6ea92-103">GetPropertyOrigin function</span></span>

<span data-ttu-id="6ea92-104">Bestimmt die Klasse, in der eine Eigenschaft deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="6ea92-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="6ea92-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ea92-105">Syntax</span></span>

```cpp
HRESULT GetPropertyOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```

## <a name="parameters"></a><span data-ttu-id="6ea92-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6ea92-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="6ea92-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="6ea92-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="6ea92-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="6ea92-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`\
<span data-ttu-id="6ea92-109">in Der Name der Eigenschaft für das Objekt, dessen besitzende Klasse angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="6ea92-109">[in] The name of the property for the object whose owning class is being requested.</span></span>

`pstrClassName`\
<span data-ttu-id="6ea92-110">vorgenommen Empfängt den Namen der Klasse, die die Eigenschaft besitzt.</span><span class="sxs-lookup"><span data-stu-id="6ea92-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="6ea92-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6ea92-111">Return value</span></span>

<span data-ttu-id="6ea92-112">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="6ea92-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6ea92-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="6ea92-113">Constant</span></span>  |<span data-ttu-id="6ea92-114">Wert</span><span class="sxs-lookup"><span data-stu-id="6ea92-114">Value</span></span>  |<span data-ttu-id="6ea92-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ea92-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="6ea92-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="6ea92-116">0x80041001</span></span> | <span data-ttu-id="6ea92-117">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6ea92-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="6ea92-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="6ea92-118">0x80041002</span></span> | <span data-ttu-id="6ea92-119">Die angegebene Eigenschaft wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="6ea92-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6ea92-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6ea92-120">0x80041008</span></span> | <span data-ttu-id="6ea92-121">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="6ea92-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="6ea92-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="6ea92-122">0x80041006</span></span> | <span data-ttu-id="6ea92-123">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6ea92-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="6ea92-124">0</span><span class="sxs-lookup"><span data-stu-id="6ea92-124">0</span></span> | <span data-ttu-id="6ea92-125">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="6ea92-125">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="6ea92-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ea92-126">Remarks</span></span>

<span data-ttu-id="6ea92-127">Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: getpropertyorigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) -Methode.</span><span class="sxs-lookup"><span data-stu-id="6ea92-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) method.</span></span>

<span data-ttu-id="6ea92-128">Da eine Klasse Eigenschaften von einer oder mehreren Basisklassen erben kann, möchten Entwickler häufig die Eigenschaft bestimmen, in der eine bestimmte Methode definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6ea92-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="6ea92-129">Der `pstrClassName` -Parameter darf nicht auf einen gültigen `BSTR` verweisen, bevor die-Funktion aufgerufen wird, `out` da es sich hierbei um einen Parameter handelt. dieser Zeiger wird nicht aufgehoben, nachdem die Funktion zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6ea92-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="6ea92-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6ea92-130">Requirements</span></span>

<span data-ttu-id="6ea92-131">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ea92-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="6ea92-132">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6ea92-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="6ea92-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6ea92-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6ea92-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ea92-134">See also</span></span>

- [<span data-ttu-id="6ea92-135">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="6ea92-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
