---
title: Blessiwbemservicesobject-Funktion (Referenz zur nicht verwalteten API)
description: Die blessiwbemservicesobject-Funktion gibt an, ob Benutzer Anmelde Informationen den Zugriff auf ein IWbemServices-Objekt zulassen.
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 1aab2076f57f938715a3e65481a3540dc52279c6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719748"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="07c7a-103">BlessIWbemServicesObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="07c7a-103">BlessIWbemServicesObject function</span></span>

<span data-ttu-id="07c7a-104">Gibt an, ob die Benutzer Anmelde Informationen den Zugriff auf ein angegebenes [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt zulassen.</span><span class="sxs-lookup"><span data-stu-id="07c7a-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="07c7a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="07c7a-105">Syntax</span></span>

```cpp
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a><span data-ttu-id="07c7a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="07c7a-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="07c7a-107">in Ein Zeiger auf ein WMI-Dienst Objekt.</span><span class="sxs-lookup"><span data-stu-id="07c7a-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="07c7a-108">in Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="07c7a-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="07c7a-109">in Das Kennwort, das zugeordnet ist `strUser` .</span><span class="sxs-lookup"><span data-stu-id="07c7a-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="07c7a-110">in Der Domänen Name des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="07c7a-110">[in] The domain name of the user.</span></span> <span data-ttu-id="07c7a-111">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="07c7a-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="07c7a-112">in Die Ebene des Identitäts Wechsels.</span><span class="sxs-lookup"><span data-stu-id="07c7a-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="07c7a-113">in Die Autorisierungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="07c7a-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="07c7a-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="07c7a-114">Return value</span></span>

<span data-ttu-id="07c7a-115">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der Header Datei " *Winerror. h* " definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="07c7a-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="07c7a-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="07c7a-116">Constant</span></span>  |<span data-ttu-id="07c7a-117">Wert</span><span class="sxs-lookup"><span data-stu-id="07c7a-117">Value</span></span>  |<span data-ttu-id="07c7a-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="07c7a-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="07c7a-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="07c7a-119">0x80070057</span></span> | <span data-ttu-id="07c7a-120">Mindestens ein Argument ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="07c7a-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="07c7a-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="07c7a-121">0x80004003</span></span> | <span data-ttu-id="07c7a-122">`pIWbemServices` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="07c7a-122">`pIWbemServices` is `null`.</span></span> |
| `E_FAIL` | <span data-ttu-id="07c7a-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="07c7a-123">0x80000008</span></span> | <span data-ttu-id="07c7a-124">Ein unbekannter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="07c7a-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="07c7a-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="07c7a-125">0x80000002</span></span> | <span data-ttu-id="07c7a-126">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="07c7a-126">Insufficient memory is available to perform the operation.</span></span> |
| `S_OK` | <span data-ttu-id="07c7a-127">0</span><span class="sxs-lookup"><span data-stu-id="07c7a-127">0</span></span> | <span data-ttu-id="07c7a-128">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="07c7a-128">The function call was successful.</span></span> |

## <a name="requirements"></a><span data-ttu-id="07c7a-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="07c7a-129">Requirements</span></span>

 <span data-ttu-id="07c7a-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07c7a-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="07c7a-131">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="07c7a-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="07c7a-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="07c7a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="07c7a-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07c7a-133">See also</span></span>

- [<span data-ttu-id="07c7a-134">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="07c7a-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
