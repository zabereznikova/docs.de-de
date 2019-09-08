---
title: EndEnumeration-Funktion (Referenz zur nicht verwalteten API)
description: Die EndEnumeration-Funktion beendet eine Enumeration.
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
ms.openlocfilehash: 0065dcd25430e102b965d5598c7e9a04c7857eb3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798811"
---
# <a name="endenumeration-function"></a><span data-ttu-id="ab7e7-103">EndEnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="ab7e7-103">EndEnumeration function</span></span>

<span data-ttu-id="ab7e7-104">Beendet eine enumerationssequenz, die mit einem Aufrufen der [beginenumeration-Funktion](beginenumeration.md)gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="ab7e7-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ab7e7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab7e7-105">Syntax</span></span>

```cpp
HRESULT EndEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```

## <a name="parameters"></a><span data-ttu-id="ab7e7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ab7e7-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="ab7e7-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ab7e7-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="ab7e7-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="ab7e7-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="ab7e7-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ab7e7-109">Return value</span></span>

<span data-ttu-id="ab7e7-110">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="ab7e7-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ab7e7-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="ab7e7-111">Constant</span></span>  |<span data-ttu-id="ab7e7-112">Wert</span><span class="sxs-lookup"><span data-stu-id="ab7e7-112">Value</span></span>  |<span data-ttu-id="ab7e7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab7e7-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="ab7e7-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ab7e7-114">0x80041001</span></span> | <span data-ttu-id="ab7e7-115">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ab7e7-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ab7e7-116">0</span><span class="sxs-lookup"><span data-stu-id="ab7e7-116">0</span></span> | <span data-ttu-id="ab7e7-117">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="ab7e7-117">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="ab7e7-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab7e7-118">Remarks</span></span>

<span data-ttu-id="ab7e7-119">Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Methode.</span><span class="sxs-lookup"><span data-stu-id="ab7e7-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="ab7e7-120">Ein aufrufsvorgang `EndEnumeration` ist nicht erforderlich, wird jedoch empfohlen, da er die der-Enumeration zugeordneten Ressourcen freigibt.</span><span class="sxs-lookup"><span data-stu-id="ab7e7-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="ab7e7-121">Die Zuordnung der Ressourcen wird jedoch automatisch aufgehoben, wenn die nächste Enumeration gestartet oder das Objekt freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ab7e7-121">However, the resources are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="ab7e7-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab7e7-122">Requirements</span></span>

<span data-ttu-id="ab7e7-123">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab7e7-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ab7e7-124">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ab7e7-124">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="ab7e7-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ab7e7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ab7e7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab7e7-126">See also</span></span>

- [<span data-ttu-id="ab7e7-127">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="ab7e7-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
