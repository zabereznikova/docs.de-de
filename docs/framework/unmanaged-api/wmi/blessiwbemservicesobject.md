---
title: BlessIWbemServicesObject-Funktion (Referenz zur nicht verwalteten API)
description: BlessIWbemServicesObject-Funktion gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf ein Objekt IWbemServices zulassen
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1eb6b870beabb71e340b0ec39c489cedb02128cf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366633"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="18208-103">BlessIWbemServicesObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="18208-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="18208-104">Gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf ein angegebenes zulassen [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) Objekt.</span><span class="sxs-lookup"><span data-stu-id="18208-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="18208-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="18208-105">Syntax</span></span>

```
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a><span data-ttu-id="18208-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="18208-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="18208-107">[in] Ein Zeiger auf ein WMI-Dienstobjekt.</span><span class="sxs-lookup"><span data-stu-id="18208-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="18208-108">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="18208-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="18208-109">[in] Das zugeordnete Kennwort `strUser`.</span><span class="sxs-lookup"><span data-stu-id="18208-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="18208-110">[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="18208-110">[in] The domain name of the user.</span></span> <span data-ttu-id="18208-111">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="18208-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="18208-112">[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="18208-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="18208-113">[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="18208-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="18208-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="18208-114">Return value</span></span>

<span data-ttu-id="18208-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *"Winerror.h"* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="18208-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="18208-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="18208-116">Constant</span></span>  |<span data-ttu-id="18208-117">Wert</span><span class="sxs-lookup"><span data-stu-id="18208-117">Value</span></span>  |<span data-ttu-id="18208-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="18208-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="18208-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="18208-119">0x80070057</span></span> | <span data-ttu-id="18208-120">Ein oder mehrere Argumente sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="18208-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="18208-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="18208-121">0x80004003</span></span> | <span data-ttu-id="18208-122">`pIWbemServices` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="18208-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="18208-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="18208-123">0x80000008</span></span> | <span data-ttu-id="18208-124">Ein Unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="18208-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="18208-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="18208-125">0x80000002</span></span> | <span data-ttu-id="18208-126">Es steht nicht genügend Arbeitsspeicher zum Ausführen des Vorgangs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="18208-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="18208-127">0</span><span class="sxs-lookup"><span data-stu-id="18208-127">0</span></span> | <span data-ttu-id="18208-128">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="18208-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="18208-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18208-129">Requirements</span></span>

 <span data-ttu-id="18208-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18208-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="18208-131">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="18208-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="18208-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="18208-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="18208-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18208-133">See also</span></span>

- [<span data-ttu-id="18208-134">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="18208-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)