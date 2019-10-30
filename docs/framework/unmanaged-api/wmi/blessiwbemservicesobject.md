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
ms.openlocfilehash: f77ff394668a235dd63cf0cddf71ea418a28125b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141684"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="90ad5-103">BlessIWbemServicesObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="90ad5-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="90ad5-104">Gibt an, ob die Benutzer Anmelde Informationen den Zugriff auf ein angegebenes [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt zulassen.</span><span class="sxs-lookup"><span data-stu-id="90ad5-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="90ad5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="90ad5-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="90ad5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="90ad5-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="90ad5-107">in Ein Zeiger auf ein WMI-Dienst Objekt.</span><span class="sxs-lookup"><span data-stu-id="90ad5-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="90ad5-108">in Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="90ad5-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="90ad5-109">in Das `strUser`zugeordnete Kennwort.</span><span class="sxs-lookup"><span data-stu-id="90ad5-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="90ad5-110">in Der Domänen Name des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="90ad5-110">[in] The domain name of the user.</span></span> <span data-ttu-id="90ad5-111">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="90ad5-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="90ad5-112">in Die Ebene des Identitäts Wechsels.</span><span class="sxs-lookup"><span data-stu-id="90ad5-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="90ad5-113">in Die Autorisierungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="90ad5-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="90ad5-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="90ad5-114">Return value</span></span>

<span data-ttu-id="90ad5-115">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der Header Datei " *Winerror. h* " definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="90ad5-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="90ad5-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="90ad5-116">Constant</span></span>  |<span data-ttu-id="90ad5-117">Wert</span><span class="sxs-lookup"><span data-stu-id="90ad5-117">Value</span></span>  |<span data-ttu-id="90ad5-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90ad5-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="90ad5-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="90ad5-119">0x80070057</span></span> | <span data-ttu-id="90ad5-120">Mindestens ein Argument ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="90ad5-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="90ad5-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="90ad5-121">0x80004003</span></span> | <span data-ttu-id="90ad5-122">`pIWbemServices` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="90ad5-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="90ad5-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="90ad5-123">0x80000008</span></span> | <span data-ttu-id="90ad5-124">Ein nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="90ad5-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="90ad5-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="90ad5-125">0x80000002</span></span> | <span data-ttu-id="90ad5-126">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="90ad5-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="90ad5-127">0</span><span class="sxs-lookup"><span data-stu-id="90ad5-127">0</span></span> | <span data-ttu-id="90ad5-128">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="90ad5-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="90ad5-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90ad5-129">Requirements</span></span>

 <span data-ttu-id="90ad5-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90ad5-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="90ad5-131">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="90ad5-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="90ad5-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="90ad5-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="90ad5-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90ad5-133">See also</span></span>

- [<span data-ttu-id="90ad5-134">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="90ad5-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
