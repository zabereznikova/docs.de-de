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
ms.openlocfilehash: adc8ea16f0ab2bf383f8a63c49ba7d61c6bac113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176447"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="2ab55-102">CreateDebuggingInterfaceFromVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="2ab55-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="2ab55-103">Erstellt ein [ICorDebug-Objekt](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) basierend auf den angegebenen Versionsinformationen.</span><span class="sxs-lookup"><span data-stu-id="2ab55-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="2ab55-104">Diese Funktion ist im .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="2ab55-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="2ab55-105">Verwenden Sie stattdessen die [ICLRRuntimeInfo::GetInterface-Methode,](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) um eine Schnittstelle für die Common Language Runtime (CLR) 2.0 abrufe, und geben Sie den Klassenbezeichner CLSID_CLRDebuggingLegacy und den Schnittstellenbezeichner IID_ICorDebug an.</span><span class="sxs-lookup"><span data-stu-id="2ab55-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="2ab55-106">Um eine Schnittstelle für CLR 4 oder höher abzurufen, rufen Sie die [CLRCreateInstance-Funktion](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) auf und geben Sie den Klassenbezeichner CLSID_CLRDebugging und den Schnittstellenbezeichner IID_ICLRDebugging an.</span><span class="sxs-lookup"><span data-stu-id="2ab55-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ab55-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ab55-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ab55-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ab55-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="2ab55-109">[in] Die Version `ICorDebug` davon wird vom Debugger erwartet.</span><span class="sxs-lookup"><span data-stu-id="2ab55-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="2ab55-110">Siehe [CorDebugInterfaceVersion-Enumeration](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) für gültige Werte.</span><span class="sxs-lookup"><span data-stu-id="2ab55-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="2ab55-111">[in] Die Common Language-Laufzeitversion, die der zu debuggenden Anwendung oder dem zu debuggenden Prozess zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="2ab55-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="2ab55-112">Informationen zum Abrufen dieses Werts finden Sie in der [GetVersionFromProcess-](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) oder [GetRequestedRuntimeVersion-Methode.](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)</span><span class="sxs-lookup"><span data-stu-id="2ab55-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="2ab55-113">[out] Die Position, die einen `ICorDebug` Zeiger auf das Objekt empfängt.</span><span class="sxs-lookup"><span data-stu-id="2ab55-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ab55-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2ab55-114">Return Value</span></span>  
 <span data-ttu-id="2ab55-115">Diese Methode gibt zusätzlich zu den folgenden Werten Standard-COM-Fehlercodes zurück, wie in der Datei WinError.h definiert.</span><span class="sxs-lookup"><span data-stu-id="2ab55-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="2ab55-116">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="2ab55-116">Return code</span></span>|<span data-ttu-id="2ab55-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ab55-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="2ab55-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ab55-118">S_OK</span></span>|<span data-ttu-id="2ab55-119">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2ab55-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="2ab55-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2ab55-120">E_INVALIDARG</span></span>|<span data-ttu-id="2ab55-121">`szDebuggeeVersion`oder `ppCordb` null ist, oder die Versionszeichenfolge ist falsch.</span><span class="sxs-lookup"><span data-stu-id="2ab55-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ab55-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2ab55-122">Remarks</span></span>  
 <span data-ttu-id="2ab55-123">Der `szDebuggeeVersion` Parameter wird der entsprechenden Version von MSCorDbi.dll zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2ab55-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ab55-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2ab55-124">Requirements</span></span>  
 <span data-ttu-id="2ab55-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ab55-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ab55-126">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2ab55-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ab55-127">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ab55-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ab55-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ab55-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab55-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ab55-129">See also</span></span>

- [<span data-ttu-id="2ab55-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="2ab55-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
