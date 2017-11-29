---
title: BlessIWbemServicesObject-Funktion (Referenz zur nicht verwalteten API)
description: Die BlessIWbemServicesObject-Funktion gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf ein Objekt IWbemServices zulassen
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BlessIWbemServicesObject
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BlessIWbemServicesObject
helpviewer_keywords: BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebba6df29b814315180e9c8e936e5e1ad175ecf8
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="f7f70-103">BlessIWbemServicesObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="f7f70-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="f7f70-104">Gibt an, ob die Anmeldeinformationen des Benutzers Zugriff auf ein angegebenes zugelassen [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) Objekt.</span><span class="sxs-lookup"><span data-stu-id="f7f70-104">Indicates whether the user credentials permit access to a specified [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f7f70-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7f70-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="f7f70-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f7f70-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="f7f70-107">[in] Ein Zeiger auf ein WMI-Dienstobjekt.</span><span class="sxs-lookup"><span data-stu-id="f7f70-107">[in] A pointer to a WMI service object.</span></span>

`strUser`  
<span data-ttu-id="f7f70-108">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="f7f70-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="f7f70-109">[in] Das zugeordnete Kennwort `strUser`.</span><span class="sxs-lookup"><span data-stu-id="f7f70-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="f7f70-110">`strAuthority`[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="f7f70-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="f7f70-111">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="f7f70-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="f7f70-112">`impLevel`[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="f7f70-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="f7f70-113">`authnLevel`[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="f7f70-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="f7f70-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f7f70-114">Return value</span></span>

<span data-ttu-id="f7f70-115">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WinError.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="f7f70-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f7f70-116">Konstante</span><span class="sxs-lookup"><span data-stu-id="f7f70-116">Constant</span></span>  |<span data-ttu-id="f7f70-117">Wert</span><span class="sxs-lookup"><span data-stu-id="f7f70-117">Value</span></span>  |<span data-ttu-id="f7f70-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7f70-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="f7f70-119">0 x 80070057</span><span class="sxs-lookup"><span data-stu-id="f7f70-119">0x80070057</span></span> | <span data-ttu-id="f7f70-120">Ein oder mehrere Argumente sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="f7f70-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="f7f70-121">0 x 80004003</span><span class="sxs-lookup"><span data-stu-id="f7f70-121">0x80004003</span></span> | <span data-ttu-id="f7f70-122">`pIWbemServices` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="f7f70-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="f7f70-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="f7f70-123">0x80000008</span></span> | <span data-ttu-id="f7f70-124">Nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f7f70-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="f7f70-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="f7f70-125">0x80000002</span></span> | <span data-ttu-id="f7f70-126">Ist nicht genügend Arbeitsspeicher zum Ausführen des Vorgangs verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7f70-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="f7f70-127">0</span><span class="sxs-lookup"><span data-stu-id="f7f70-127">0</span></span> | <span data-ttu-id="f7f70-128">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="f7f70-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="f7f70-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f7f70-129">Requirements</span></span>  
 <span data-ttu-id="f7f70-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7f70-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7f70-131">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f7f70-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f7f70-132">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f7f70-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f70-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7f70-133">See also</span></span>  
[<span data-ttu-id="f7f70-134">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="f7f70-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
