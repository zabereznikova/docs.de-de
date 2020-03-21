---
title: BlessIWbemServicesObject-Funktion (Nicht verwaltete API-Referenz)
description: Die Funktion BlessIWbemServicesObject gibt an, ob Benutzeranmeldeinformationen den Zugriff auf ein IWbemServices-Objekt zulassen.
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
ms.openlocfilehash: fd822f78d29ad3a75fb5e57dd7c23b7049d445b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175030"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="eae71-103">BlessIWbemServicesObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="eae71-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="eae71-104">Gibt an, ob die Benutzeranmeldeinformationen den Zugriff auf ein angegebenes [IWbemServices-Objekt](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) zulassen.</span><span class="sxs-lookup"><span data-stu-id="eae71-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="eae71-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="eae71-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="eae71-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="eae71-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="eae71-107">[in] Ein Zeiger auf ein WMI-Dienstobjekt.</span><span class="sxs-lookup"><span data-stu-id="eae71-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="eae71-108">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="eae71-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="eae71-109">[in] Das Kennwort, `strUser`das mit verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="eae71-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="eae71-110">[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="eae71-110">[in] The domain name of the user.</span></span> <span data-ttu-id="eae71-111">Weitere Informationen finden Sie in der [ConnectServerWmi-Funktion.](connectserverwmi.md)</span><span class="sxs-lookup"><span data-stu-id="eae71-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="eae71-112">[in] Die Identitätswechselebene.</span><span class="sxs-lookup"><span data-stu-id="eae71-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="eae71-113">[in] Die Berechtigungsstufe.</span><span class="sxs-lookup"><span data-stu-id="eae71-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="eae71-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="eae71-114">Return value</span></span>

<span data-ttu-id="eae71-115">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *WinError.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="eae71-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="eae71-116">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="eae71-116">Constant</span></span>  |<span data-ttu-id="eae71-117">value</span><span class="sxs-lookup"><span data-stu-id="eae71-117">Value</span></span>  |<span data-ttu-id="eae71-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eae71-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="eae71-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="eae71-119">0x80070057</span></span> | <span data-ttu-id="eae71-120">Mindestens ein Argument ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="eae71-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="eae71-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="eae71-121">0x80004003</span></span> | <span data-ttu-id="eae71-122">`pIWbemServices` ist `null`</span><span class="sxs-lookup"><span data-stu-id="eae71-122">`pIWbemServices` is `null`.</span></span> |
| `E_FAIL` | <span data-ttu-id="eae71-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="eae71-123">0x80000008</span></span> | <span data-ttu-id="eae71-124">Ein unbekannter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="eae71-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="eae71-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="eae71-125">0x80000002</span></span> | <span data-ttu-id="eae71-126">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="eae71-126">Insufficient memory is available to perform the operation.</span></span> |
| `S_OK` | <span data-ttu-id="eae71-127">0</span><span class="sxs-lookup"><span data-stu-id="eae71-127">0</span></span> | <span data-ttu-id="eae71-128">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="eae71-128">The function call was successful.</span></span> |

## <a name="requirements"></a><span data-ttu-id="eae71-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="eae71-129">Requirements</span></span>

 <span data-ttu-id="eae71-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eae71-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="eae71-131">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="eae71-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="eae71-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="eae71-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="eae71-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eae71-133">See also</span></span>

- [<span data-ttu-id="eae71-134">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="eae71-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
