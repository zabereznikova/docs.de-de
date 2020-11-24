---
title: Getqualifierset-Funktion (Referenz zur nicht verwalteten API)
description: Die getqualifierset-Funktion Ruft den Qualifizierer Satz für eine Klasse oder eine Instanz ab.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f9bb882a0f62499167b79bf3e6691d05e394720f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671342"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="54bce-103">GetQualifierSet-Funktion</span><span class="sxs-lookup"><span data-stu-id="54bce-103">GetQualifierSet function</span></span>

<span data-ttu-id="54bce-104">Ruft den Qualifizierer ab, der für eine Klasseninstanz oder eine Klassendefinition festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="54bce-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="54bce-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="54bce-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a><span data-ttu-id="54bce-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="54bce-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="54bce-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="54bce-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="54bce-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="54bce-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="54bce-109">vorgenommen Empfängt den Schnittstellen Zeiger, der den Zugriff auf die Qualifizierer des Klassen Objekts zulässt.</span><span class="sxs-lookup"><span data-stu-id="54bce-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="54bce-110">`ppQualSet` darf nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="54bce-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="54bce-111">Wenn ein Fehler auftritt, wird kein neues Objekt zurückgegeben, und der Zeiger bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="54bce-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="54bce-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="54bce-112">Return value</span></span>

<span data-ttu-id="54bce-113">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="54bce-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="54bce-114">Konstante</span><span class="sxs-lookup"><span data-stu-id="54bce-114">Constant</span></span>  |<span data-ttu-id="54bce-115">Wert</span><span class="sxs-lookup"><span data-stu-id="54bce-115">Value</span></span>  |<span data-ttu-id="54bce-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="54bce-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="54bce-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="54bce-117">0x80041001</span></span> | <span data-ttu-id="54bce-118">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="54bce-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="54bce-119">0x80041002 angezeigt</span><span class="sxs-lookup"><span data-stu-id="54bce-119">0x80041002</span></span> | <span data-ttu-id="54bce-120">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="54bce-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="54bce-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="54bce-121">0x80041006</span></span> | <span data-ttu-id="54bce-122">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="54bce-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="54bce-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="54bce-123">0x80041008</span></span> | <span data-ttu-id="54bce-124">Ein-Parameter ist `null` .</span><span class="sxs-lookup"><span data-stu-id="54bce-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="54bce-125">0</span><span class="sxs-lookup"><span data-stu-id="54bce-125">0</span></span> | <span data-ttu-id="54bce-126">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="54bce-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="54bce-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="54bce-127">Remarks</span></span>

<span data-ttu-id="54bce-128">Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: getqualifierset](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) -Methode.</span><span class="sxs-lookup"><span data-stu-id="54bce-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span>

<span data-ttu-id="54bce-129">Der [iwbemqualifierset-Zeiger](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) ermöglicht dem Aufrufer, diese Qualifizierer hinzuzufügen, zu bearbeiten oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="54bce-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="54bce-130">Solche hinzugefügten, bearbeiteten oder gelöschten Qualifizierer gelten für die gesamte-Instanz oder-Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="54bce-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="54bce-131">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="54bce-131">Requirements</span></span>  

<span data-ttu-id="54bce-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54bce-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54bce-133">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="54bce-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="54bce-134">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="54bce-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54bce-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54bce-135">See also</span></span>

- [<span data-ttu-id="54bce-136">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="54bce-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
