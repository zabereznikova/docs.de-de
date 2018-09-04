---
title: BlessIWbemServices-Funktion (Referenz zur nicht verwalteten API)
description: BlessIWbemServices-Funktion gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf eine Klasse IWbemServices zulassen.
ms.date: 11/06/2017
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
ms.openlocfilehash: a65c3c14507b2520c69875a1bc101ce826ace7ba
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532164"
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="67a84-103">BlessIWbemServices-Funktion</span><span class="sxs-lookup"><span data-stu-id="67a84-103">BlessIWbemServices function</span></span>
<span data-ttu-id="67a84-104">Gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf den angegebenen zulassen [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) Klasse.</span><span class="sxs-lookup"><span data-stu-id="67a84-104">Indicates whether the user credentials permit access to the specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) class.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="67a84-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="67a84-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="67a84-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="67a84-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="67a84-107">[in] Ein Zeiger auf die [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) Objekt für die Berechtigungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="67a84-107">[in] A pointer to the [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object for which permissions are required.</span></span>

`strUser`  
<span data-ttu-id="67a84-108">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="67a84-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="67a84-109">[in] Das zugeordnete Kennwort `strUser`.</span><span class="sxs-lookup"><span data-stu-id="67a84-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="67a84-110">`strAuthority` [in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="67a84-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="67a84-111">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="67a84-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="67a84-112">`impLevel` [in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="67a84-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="67a84-113">`authnLevel` [in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="67a84-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="67a84-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="67a84-114">Return value</span></span>

<span data-ttu-id="67a84-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *"Winerror.h"* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="67a84-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="67a84-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="67a84-116">Constant</span></span>  |<span data-ttu-id="67a84-117">Wert</span><span class="sxs-lookup"><span data-stu-id="67a84-117">Value</span></span>  |<span data-ttu-id="67a84-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67a84-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="67a84-119">0 x 80070057</span><span class="sxs-lookup"><span data-stu-id="67a84-119">0x80070057</span></span> | <span data-ttu-id="67a84-120">Ein oder mehrere Argumente sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="67a84-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="67a84-121">0 x 80004003</span><span class="sxs-lookup"><span data-stu-id="67a84-121">0x80004003</span></span> | <span data-ttu-id="67a84-122">`pIWbemServices` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="67a84-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="67a84-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="67a84-123">0x80000008</span></span> | <span data-ttu-id="67a84-124">Ein Unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="67a84-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="67a84-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="67a84-125">0x80000002</span></span> | <span data-ttu-id="67a84-126">Es steht nicht genügend Arbeitsspeicher zum Ausführen des Vorgangs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="67a84-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="67a84-127">0</span><span class="sxs-lookup"><span data-stu-id="67a84-127">0</span></span> | <span data-ttu-id="67a84-128">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="67a84-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="67a84-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67a84-129">Requirements</span></span>  
 <span data-ttu-id="67a84-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67a84-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67a84-131">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="67a84-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="67a84-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="67a84-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a84-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67a84-133">See also</span></span>  
[<span data-ttu-id="67a84-134">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="67a84-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
