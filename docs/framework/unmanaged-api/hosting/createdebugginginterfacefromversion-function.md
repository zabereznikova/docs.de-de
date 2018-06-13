---
title: CreateDebuggingInterfaceFromVersion-Funktion
ms.date: 03/30/2017
api_name:
- CreateDebuggingInterfaceFromVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function [.NET Framework hosting]
ms.assetid: a746a849-463c-44f5-a2f0-9e812ed8bcc3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b51b924652019cf05401e1972797c18e74b82d3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431547"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="1aa1d-102">CreateDebuggingInterfaceFromVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="1aa1d-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="1aa1d-103">Erstellt ein [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) -Objekt auf Grundlage der angegebenen Versionsinformationen.</span><span class="sxs-lookup"><span data-stu-id="1aa1d-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="1aa1d-104">Diese Funktion ist veraltet, in der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1aa1d-104">This function is obsolete in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="1aa1d-105">Um eine Schnittstelle für die common Language Runtime (CLR) 2.0 zu erhalten, verwenden Sie stattdessen die [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) Methode, und geben Sie die Klassen-ID CLSID_CLRDebuggingLegacy und der Schnittstellenbezeichner IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="1aa1d-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="1aa1d-106">Rufen Sie eine Schnittstelle für CLR 4 oder höher Aufrufen der [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) Funktion, und geben Sie die Klassen-ID CLSID_CLRDebugging und der Schnittstellenbezeichner IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="1aa1d-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aa1d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="1aa1d-107">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1aa1d-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="1aa1d-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="1aa1d-109">[in] Die Version des `ICorDebug` , die vom Debugger erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="1aa1d-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="1aa1d-110">Finden Sie unter der [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) Enumeration für gültige Werte.</span><span class="sxs-lookup"><span data-stu-id="1aa1d-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="1aa1d-111">[in] Version der common Language Runtime die Anwendung oder den Prozess zu debuggende zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1aa1d-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="1aa1d-112">Finden Sie unter der [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) oder [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) -Methode Informationen zum Abrufen dieses Werts.</span><span class="sxs-lookup"><span data-stu-id="1aa1d-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="1aa1d-113">[out] Der Speicherort, empfängt einen Zeiger auf, die `ICorDebug` Objekt.</span><span class="sxs-lookup"><span data-stu-id="1aa1d-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1aa1d-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1aa1d-114">Return Value</span></span>  
 <span data-ttu-id="1aa1d-115">Diese Methode gibt die standard-COM-Fehlercodes zurück, wie in der Datei "WinError.h" zusätzlich zu den folgenden Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="1aa1d-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="1aa1d-116">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="1aa1d-116">Return code</span></span>|<span data-ttu-id="1aa1d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1aa1d-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1aa1d-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="1aa1d-118">S_OK</span></span>|<span data-ttu-id="1aa1d-119">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1aa1d-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="1aa1d-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1aa1d-120">E_INVALIDARG</span></span>|<span data-ttu-id="1aa1d-121">`szDebuggeeVersion` oder `ppCordb` ist Null, oder die Version Zeichenfolge ist falsch.</span><span class="sxs-lookup"><span data-stu-id="1aa1d-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1aa1d-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1aa1d-122">Remarks</span></span>  
 <span data-ttu-id="1aa1d-123">Die `szDebuggeeVersion` aufgeführte Parameter wird die entsprechende Version von "mscordbi.dll".</span><span class="sxs-lookup"><span data-stu-id="1aa1d-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aa1d-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1aa1d-124">Requirements</span></span>  
 <span data-ttu-id="1aa1d-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1aa1d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aa1d-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1aa1d-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1aa1d-127">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="1aa1d-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1aa1d-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aa1d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aa1d-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1aa1d-129">See Also</span></span>  
 [<span data-ttu-id="1aa1d-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="1aa1d-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
