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
ms.openlocfilehash: 247383e267ab3e8932d43621e122986a59d9a30d
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490508"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="83234-102">CreateDebuggingInterfaceFromVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="83234-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="83234-103">Erstellt eine [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) -Objekt auf Grundlage der angegebenen Versionsinformationen.</span><span class="sxs-lookup"><span data-stu-id="83234-103">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="83234-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="83234-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="83234-105">Um eine Schnittstelle für die common Language Runtime (CLR) 2.0 zu erhalten, verwenden Sie stattdessen die [ICLRRuntimeInfo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) Methode, und geben Sie die Klassen-ID CLSID_CLRDebuggingLegacy und der schnittstellenkennung IID_ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="83234-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="83234-106">Erhalten eine Schnittstelle für die CLR 4 oder höher, rufen Sie die [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) Funktion, und geben Sie die Klassen-ID CLSID_CLRDebugging und der schnittstellenkennung IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="83234-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83234-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="83234-107">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,   
    [in]  LPCWSTR  szDebuggeeVersion,   
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83234-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="83234-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="83234-109">[in] Die Version des `ICorDebug` , die vom Debugger erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="83234-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="83234-110">Finden Sie unter den [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) -Enumeration für gültige Werte.</span><span class="sxs-lookup"><span data-stu-id="83234-110">See the [CorDebugInterfaceVersion](../../../../docs/framework/unmanaged-api/debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="83234-111">[in] Version der common Language Runtime die Anwendung oder den Prozess zu debuggende zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="83234-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="83234-112">Finden Sie unter den [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) oder [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) Methode für die Informationen zum Abrufen dieses Werts.</span><span class="sxs-lookup"><span data-stu-id="83234-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="83234-113">[out] Der Speicherort, der einen Zeiger auf empfängt die `ICorDebug` Objekt.</span><span class="sxs-lookup"><span data-stu-id="83234-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83234-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="83234-114">Return Value</span></span>  
 <span data-ttu-id="83234-115">Diese Methode gibt die standard-COM-Fehlercodes zurück, wie in der Datei "Winerror.h", zusätzlich zu den folgenden Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="83234-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="83234-116">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="83234-116">Return code</span></span>|<span data-ttu-id="83234-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83234-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="83234-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="83234-118">S_OK</span></span>|<span data-ttu-id="83234-119">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="83234-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="83234-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="83234-120">E_INVALIDARG</span></span>|<span data-ttu-id="83234-121">`szDebuggeeVersion` oder `ppCordb` ist Null, oder die Version Zeichenfolge ist falsch.</span><span class="sxs-lookup"><span data-stu-id="83234-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83234-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83234-122">Remarks</span></span>  
 <span data-ttu-id="83234-123">Die `szDebuggeeVersion` Parameter ist die entsprechende Version von "mscordbi.dll" zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="83234-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83234-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83234-124">Requirements</span></span>  
 <span data-ttu-id="83234-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83234-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83234-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="83234-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83234-127">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83234-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83234-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83234-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83234-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83234-129">See also</span></span>

- [<span data-ttu-id="83234-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="83234-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
