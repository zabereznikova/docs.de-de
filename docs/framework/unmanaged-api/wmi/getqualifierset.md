---
title: GetQualifierSet-Funktion (Nicht verwaltete API-Referenz)
description: Die GetQualifierSet-Funktion ruft den Qualifizierersatz für eine Klasse oder Instanz ab.
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
ms.openlocfilehash: 368f0a13871bd48780fa30b370d37157d2724bb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176772"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="02752-103">GetQualifierSet-Funktion</span><span class="sxs-lookup"><span data-stu-id="02752-103">GetQualifierSet function</span></span>
<span data-ttu-id="02752-104">Ruft den Qualifizierer ab, der für eine Klasseninstanz oder eine Klassendefinition festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="02752-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="02752-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="02752-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a><span data-ttu-id="02752-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="02752-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="02752-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="02752-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="02752-108">[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="02752-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="02752-109">[out] Empfängt den Schnittstellenzeiger, der den Zugriff auf die Qualifizierer des Klassenobjekts ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="02752-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="02752-110">`ppQualSet` darf nicht `null` sein.</span><span class="sxs-lookup"><span data-stu-id="02752-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="02752-111">Wenn ein Fehler auftritt, wird kein neues Objekt zurückgegeben, und der Zeiger bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="02752-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="02752-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="02752-112">Return value</span></span>

<span data-ttu-id="02752-113">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="02752-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="02752-114">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="02752-114">Constant</span></span>  |<span data-ttu-id="02752-115">value</span><span class="sxs-lookup"><span data-stu-id="02752-115">Value</span></span>  |<span data-ttu-id="02752-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02752-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="02752-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="02752-117">0x80041001</span></span> | <span data-ttu-id="02752-118">Es ist ein allgemeines Versagen aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="02752-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="02752-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="02752-119">0x80041002</span></span> | <span data-ttu-id="02752-120">Die angegebene Methode ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="02752-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="02752-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="02752-121">0x80041006</span></span> | <span data-ttu-id="02752-122">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="02752-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="02752-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="02752-123">0x80041008</span></span> | <span data-ttu-id="02752-124">Ein Parameter `null`ist .</span><span class="sxs-lookup"><span data-stu-id="02752-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="02752-125">0</span><span class="sxs-lookup"><span data-stu-id="02752-125">0</span></span> | <span data-ttu-id="02752-126">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="02752-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="02752-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="02752-127">Remarks</span></span>

<span data-ttu-id="02752-128">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::GetQualifierSet-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset)</span><span class="sxs-lookup"><span data-stu-id="02752-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span>

<span data-ttu-id="02752-129">Mit dem [IWbemQualifierSet-Zeiger](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) kann der Aufrufer diese Qualifizierer hinzufügen, bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="02752-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="02752-130">Solche hinzugefügten, bearbeiteten oder gelöschten Qualifizierer gelten für die gesamte Instanz- oder Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="02752-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="02752-131">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="02752-131">Requirements</span></span>  
<span data-ttu-id="02752-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02752-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02752-133">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="02752-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="02752-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="02752-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02752-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02752-135">See also</span></span>

- [<span data-ttu-id="02752-136">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="02752-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
