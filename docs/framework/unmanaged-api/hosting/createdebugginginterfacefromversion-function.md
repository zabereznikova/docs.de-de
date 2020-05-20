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
ms.openlocfilehash: 0e1395229b67c4054df62935375a4136edf63078
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616488"
---
# <a name="createdebugginginterfacefromversion-function"></a><span data-ttu-id="91a96-102">CreateDebuggingInterfaceFromVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="91a96-102">CreateDebuggingInterfaceFromVersion Function</span></span>
<span data-ttu-id="91a96-103">Erstellt ein [ICorDebug](../debugging/icordebug-interface.md) -Objekt auf Grundlage der angegebenen Versionsinformationen.</span><span class="sxs-lookup"><span data-stu-id="91a96-103">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 <span data-ttu-id="91a96-104">Diese Funktion ist in der .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="91a96-104">This function is obsolete in the .NET Framework 4.</span></span> <span data-ttu-id="91a96-105">Verwenden Sie stattdessen die [iclrruntimeingefo:: GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) -Methode, und geben Sie den Klassen Bezeichner CLSID_CLRDebuggingLegacy und den Schnittstellen Bezeichner IID_ICorDebug an, um eine Schnittstelle für die Common Language Runtime (CLR) 2,0 abzurufen.</span><span class="sxs-lookup"><span data-stu-id="91a96-105">Instead, to get an interface for the common language runtime (CLR) 2.0, use the [ICLRRuntimeInfo::GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) method and specify the class identifier CLSID_CLRDebuggingLegacy and the interface identifier IID_ICorDebug.</span></span> <span data-ttu-id="91a96-106">Um eine Schnittstelle für CLR 4 oder höher abzurufen, müssen Sie die [clrkreateinstance](clrcreateinstance-function.md) -Funktion aufrufen und die Klassen-ID CLSID_CLRDebugging und den Schnittstellen Bezeichner IID_ICLRDebugging angeben.</span><span class="sxs-lookup"><span data-stu-id="91a96-106">To get an interface for CLR 4 or later, call the [CLRCreateInstance](clrcreateinstance-function.md) function and specify the class identifier CLSID_CLRDebugging and the interface identifier IID_ICLRDebugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a96-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="91a96-107">Syntax</span></span>  
  
```cpp  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  int      iDebuggerVersion,
    [in]  LPCWSTR  szDebuggeeVersion,
    [out] IUnknown **ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91a96-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="91a96-108">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="91a96-109">in Die Version von `ICorDebug` , die vom Debugger erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="91a96-109">[in] The version of `ICorDebug` that is expected by the debugger.</span></span> <span data-ttu-id="91a96-110">Gültige Werte finden Sie in der [Cordebug](../debugging/cordebuginterfaceversion-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="91a96-110">See the [CorDebugInterfaceVersion](../debugging/cordebuginterfaceversion-enumeration.md) enumeration for valid values.</span></span>  
  
 `szDebuggeeVersion`  
 <span data-ttu-id="91a96-111">in Die Common Language Runtime Version, die der zu debuggenden Anwendung oder dem Prozess zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="91a96-111">[in] The common language runtime version associated with the application or process to be debugged.</span></span> <span data-ttu-id="91a96-112">Informationen zum Abrufen dieses Werts finden Sie in der [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) -Methode oder der [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="91a96-112">See the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) or [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md) method for information on retrieving this value.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="91a96-113">vorgenommen Der Speicherort, der einen Zeiger auf das- `ICorDebug` Objekt empfängt.</span><span class="sxs-lookup"><span data-stu-id="91a96-113">[out] The location that receives a pointer to the `ICorDebug` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91a96-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="91a96-114">Return Value</span></span>  
 <span data-ttu-id="91a96-115">Diese Methode gibt Standard-COM-Fehlercodes zurück, wie in der Datei "Winerror. h" zusätzlich zu den folgenden Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="91a96-115">This method returns standard COM error codes as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="91a96-116">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="91a96-116">Return code</span></span>|<span data-ttu-id="91a96-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="91a96-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="91a96-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="91a96-118">S_OK</span></span>|<span data-ttu-id="91a96-119">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="91a96-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="91a96-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="91a96-120">E_INVALIDARG</span></span>|<span data-ttu-id="91a96-121">`szDebuggeeVersion`oder `ppCordb` ist NULL, oder die Versions Zeichenfolge ist falsch.</span><span class="sxs-lookup"><span data-stu-id="91a96-121">`szDebuggeeVersion` or `ppCordb` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91a96-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91a96-122">Remarks</span></span>  
 <span data-ttu-id="91a96-123">Der- `szDebuggeeVersion` Parameter wird der entsprechenden Version von mscordbi. dll zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="91a96-123">The `szDebuggeeVersion` parameter maps to the corresponding version of MSCorDbi.dll.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91a96-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91a96-124">Requirements</span></span>  
 <span data-ttu-id="91a96-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91a96-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91a96-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="91a96-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91a96-127">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="91a96-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91a96-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91a96-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a96-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91a96-129">See also</span></span>

- [<span data-ttu-id="91a96-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="91a96-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
