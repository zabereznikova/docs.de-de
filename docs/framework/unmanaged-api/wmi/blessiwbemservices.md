---
title: BlessIWbemServices-Funktion (Referenz zur nicht verwalteten API)
description: Die BlessIWbemServices-Funktion gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf eine Klasse IWbemServices zuzulassen.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f384e8d045dd7a6f2f864f0991f8caf4a674408b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="009b7-103">BlessIWbemServices-Funktion</span><span class="sxs-lookup"><span data-stu-id="009b7-103">BlessIWbemServices function</span></span>
<span data-ttu-id="009b7-104">Gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf den angegebenen zugelassen [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) Klasse.</span><span class="sxs-lookup"><span data-stu-id="009b7-104">Indicates whether the user credentials permit access to the specified [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) class.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="009b7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="009b7-105">Syntax</span></span>  
  
```  
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="009b7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="009b7-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="009b7-107">[in] Ein Zeiger auf die [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) Objekt für die Berechtigungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="009b7-107">[in] A pointer to the [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object for which permissions are required.</span></span>

`strUser`  
<span data-ttu-id="009b7-108">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="009b7-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="009b7-109">[in] Das zugeordnete Kennwort `strUser`.</span><span class="sxs-lookup"><span data-stu-id="009b7-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="009b7-110">`strAuthority`[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="009b7-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="009b7-111">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="009b7-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="009b7-112">`impLevel`[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="009b7-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="009b7-113">`authnLevel`[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="009b7-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="009b7-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="009b7-114">Return value</span></span>

<span data-ttu-id="009b7-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WinError.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="009b7-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="009b7-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="009b7-116">Constant</span></span>  |<span data-ttu-id="009b7-117">Wert</span><span class="sxs-lookup"><span data-stu-id="009b7-117">Value</span></span>  |<span data-ttu-id="009b7-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="009b7-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="009b7-119">0 x 80070057</span><span class="sxs-lookup"><span data-stu-id="009b7-119">0x80070057</span></span> | <span data-ttu-id="009b7-120">Ein oder mehrere Argumente sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="009b7-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="009b7-121">0 x 80004003</span><span class="sxs-lookup"><span data-stu-id="009b7-121">0x80004003</span></span> | <span data-ttu-id="009b7-122">`pIWbemServices` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="009b7-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="009b7-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="009b7-123">0x80000008</span></span> | <span data-ttu-id="009b7-124">Nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="009b7-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="009b7-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="009b7-125">0x80000002</span></span> | <span data-ttu-id="009b7-126">Ist nicht genügend Arbeitsspeicher zum Ausführen des Vorgangs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="009b7-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="009b7-127">0</span><span class="sxs-lookup"><span data-stu-id="009b7-127">0</span></span> | <span data-ttu-id="009b7-128">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="009b7-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="009b7-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="009b7-129">Requirements</span></span>  
 <span data-ttu-id="009b7-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="009b7-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="009b7-131">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="009b7-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="009b7-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="009b7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="009b7-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="009b7-133">See also</span></span>  
[<span data-ttu-id="009b7-134">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="009b7-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
