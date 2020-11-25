---
title: CorPinvokeMap-Enumeration
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
ms.openlocfilehash: da3ee54b1c3361149c11a9cfad8bdb07a5007ecf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706137"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="893d7-102">CorPinvokeMap-Enumeration</span><span class="sxs-lookup"><span data-stu-id="893d7-102">CorPinvokeMap Enumeration</span></span>

<span data-ttu-id="893d7-103">Gibt Optionen für einen PInvoke-Befehl an.</span><span class="sxs-lookup"><span data-stu-id="893d7-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="893d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="893d7-104">Syntax</span></span>  
  
```cpp  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a><span data-ttu-id="893d7-105">Member</span><span class="sxs-lookup"><span data-stu-id="893d7-105">Members</span></span>  
  
|<span data-ttu-id="893d7-106">Member</span><span class="sxs-lookup"><span data-stu-id="893d7-106">Member</span></span>|<span data-ttu-id="893d7-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="893d7-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="893d7-108">Verwenden Sie die einzelnen Elementnamen wie angegeben.</span><span class="sxs-lookup"><span data-stu-id="893d7-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="893d7-109">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="893d7-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="893d7-110">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="893d7-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="893d7-111">Marshallt Zeichenfolgen als Mehrfachbyte-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="893d7-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="893d7-112">Marshallt Zeichenfolgen als 2-Byte-Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="893d7-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="893d7-113">Marshallt Zeichenfolgen automatisch entsprechend dem Zielbetriebssystem.</span><span class="sxs-lookup"><span data-stu-id="893d7-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="893d7-114">Der Standardwert ist Unicode unter Windows NT, Windows 2000, Windows XP und der Windows Server 2003-Familie. der Standardwert ist ANSI unter Windows 98 und Windows Me.</span><span class="sxs-lookup"><span data-stu-id="893d7-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="893d7-115">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="893d7-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="893d7-116">Führt eine Zuordnung mit einer optimalen Anpassung von Unicode-Zeichen durch, bei denen keine genaue Entsprechung im ANSI-Zeichensatz vorliegt.</span><span class="sxs-lookup"><span data-stu-id="893d7-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="893d7-117">Führen Sie keine Zuordnung mit einer optimalen Anpassung von Unicode-Zeichen durch.</span><span class="sxs-lookup"><span data-stu-id="893d7-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="893d7-118">In diesem Fall werden alle nicht mappbaren Zeichen durch ein "?" ersetzt.</span><span class="sxs-lookup"><span data-stu-id="893d7-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="893d7-119">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="893d7-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="893d7-120">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="893d7-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="893d7-121">Löst eine Ausnahme aus, wenn der Interop-Mars Haller auf ein nicht mappbares Zeichen stößt.</span><span class="sxs-lookup"><span data-stu-id="893d7-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="893d7-122">Lösen Sie keine Ausnahme aus, wenn der Interop-Mars Haller auf ein nicht mappbares Zeichen stößt.</span><span class="sxs-lookup"><span data-stu-id="893d7-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="893d7-123">Reserviert</span><span class="sxs-lookup"><span data-stu-id="893d7-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="893d7-124">Ermöglicht dem aufgerufenen das Abrufen der Win32- `SetLastError` Funktion vor der Rückgabe von der attributierten Methode.</span><span class="sxs-lookup"><span data-stu-id="893d7-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="893d7-125">Reserviert</span><span class="sxs-lookup"><span data-stu-id="893d7-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="893d7-126">Verwenden Sie die standardmäßige Platt Form Aufruf Konvention.</span><span class="sxs-lookup"><span data-stu-id="893d7-126">Use the default platform calling convention.</span></span> <span data-ttu-id="893d7-127">Beispielsweise ist unter Windows der Standardwert, `StdCall` und auf Windows CE .net ist er `Cdecl` .</span><span class="sxs-lookup"><span data-stu-id="893d7-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="893d7-128">Verwenden Sie die `Cdecl` Aufruf Konvention.</span><span class="sxs-lookup"><span data-stu-id="893d7-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="893d7-129">In diesem Fall bereinigt der Aufrufer den Stapel.</span><span class="sxs-lookup"><span data-stu-id="893d7-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="893d7-130">Dies ermöglicht das Aufrufen von Funktionen mit `varargs` (d. h. Funktionen, die eine Variable Anzahl von Parametern akzeptieren).</span><span class="sxs-lookup"><span data-stu-id="893d7-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="893d7-131">Verwenden Sie die `StdCall` Aufruf Konvention.</span><span class="sxs-lookup"><span data-stu-id="893d7-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="893d7-132">In diesem Fall bereinigt der aufgerufene den Stapel.</span><span class="sxs-lookup"><span data-stu-id="893d7-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="893d7-133">Dies ist die Standardkonvention für das Aufrufen nicht verwalteter Funktionen mit Plattformaufruf.</span><span class="sxs-lookup"><span data-stu-id="893d7-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="893d7-134">Verwenden Sie die `ThisCall` Aufruf Konvention.</span><span class="sxs-lookup"><span data-stu-id="893d7-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="893d7-135">In diesem Fall ist der erste Parameter der `this` Zeiger und wird in Register ECX gespeichert.</span><span class="sxs-lookup"><span data-stu-id="893d7-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="893d7-136">Weitere Parameter werden in den Stapel verschoben.</span><span class="sxs-lookup"><span data-stu-id="893d7-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="893d7-137">Die `ThisCall` Aufruf Konvention wird zum Aufrufen von Methoden für Klassen verwendet, die aus einer nicht verwalteten DLL exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="893d7-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="893d7-138">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="893d7-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="893d7-139">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="893d7-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="893d7-140">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="893d7-140">Requirements</span></span>  

 <span data-ttu-id="893d7-141">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="893d7-141">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="893d7-142">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="893d7-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="893d7-143">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="893d7-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="893d7-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="893d7-144">See also</span></span>

- [<span data-ttu-id="893d7-145">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="893d7-145">Metadata Enumerations</span></span>](metadata-enumerations.md)
