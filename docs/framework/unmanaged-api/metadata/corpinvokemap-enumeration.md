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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 951941092f67f66c5b17c8ae592569c2a8e6a675
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079629"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="6db09-102">CorPinvokeMap-Enumeration</span><span class="sxs-lookup"><span data-stu-id="6db09-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="6db09-103">Gibt Optionen für PInvoke-Aufrufs.</span><span class="sxs-lookup"><span data-stu-id="6db09-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6db09-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6db09-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="6db09-105">Member</span><span class="sxs-lookup"><span data-stu-id="6db09-105">Members</span></span>  
  
|<span data-ttu-id="6db09-106">Member</span><span class="sxs-lookup"><span data-stu-id="6db09-106">Member</span></span>|<span data-ttu-id="6db09-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6db09-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="6db09-108">Verwenden Sie alle Elementnamen, wie angegeben.</span><span class="sxs-lookup"><span data-stu-id="6db09-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="6db09-109">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="6db09-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="6db09-110">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="6db09-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="6db09-111">Marshallt Zeichenfolgen als Zeichenfolgen mit mehreren Byte-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6db09-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="6db09-112">Marshallt Zeichenfolgen als 2-Byte-Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6db09-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="6db09-113">Automatisch zu marshallen Zeichenfolgen entsprechend dem Zielbetriebssystem bereit.</span><span class="sxs-lookup"><span data-stu-id="6db09-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="6db09-114">Der Standardwert ist Unicode unter Windows NT, Windows 2000, Windows XP und Windows Server 2003-Familie; Der Standardwert ist ANSI unter Windows 98 und Windows Me enthalten.</span><span class="sxs-lookup"><span data-stu-id="6db09-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="6db09-115">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="6db09-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="6db09-116">Führen Sie die Zuordnung mit ähnlichen Zeichen von Unicode-Zeichen, die eine genaue Übereinstimmung in die ANSI-Zeichensatz ausgewählt hat.</span><span class="sxs-lookup"><span data-stu-id="6db09-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="6db09-117">Führen Sie die Zuordnung mit ähnlichen Zeichen von Unicode-Zeichen nicht zu.</span><span class="sxs-lookup"><span data-stu-id="6db09-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="6db09-118">In diesem Fall alle nicht zuzuordnenden Zeichen ersetzt werden durch ein "?".</span><span class="sxs-lookup"><span data-stu-id="6db09-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="6db09-119">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="6db09-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="6db09-120">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="6db09-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="6db09-121">Wenn es sich bei der Interop-Marshaller ein nicht zuzuordnendes Zeichen findet, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6db09-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="6db09-122">Keine Ausnahme ausgelöst, wenn der interop-Marshaller ein nicht zuzuordnendes Zeichen erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="6db09-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="6db09-123">Reserviert</span><span class="sxs-lookup"><span data-stu-id="6db09-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="6db09-124">Ermöglicht es dem aufgerufenen die Win32-Aufrufen `SetLastError` vor dem Zurückgeben aus die attributierte Methode.</span><span class="sxs-lookup"><span data-stu-id="6db09-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="6db09-125">Reserviert</span><span class="sxs-lookup"><span data-stu-id="6db09-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="6db09-126">Verwenden Sie die Standardkonvention für Plattformaufrufe.</span><span class="sxs-lookup"><span data-stu-id="6db09-126">Use the default platform calling convention.</span></span> <span data-ttu-id="6db09-127">Für Windows ist der Standardwert beispielsweise `StdCall` und auf Windows CE .NET ist `Cdecl`.</span><span class="sxs-lookup"><span data-stu-id="6db09-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="6db09-128">Verwenden der `Cdecl` Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="6db09-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="6db09-129">Der Aufrufer entleert in diesem Fall den Stapel.</span><span class="sxs-lookup"><span data-stu-id="6db09-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="6db09-130">Dies aktiviert Aufruffunktionen mit `varargs` (d. h. Funktionen, die eine Variable Anzahl von Parametern akzeptieren).</span><span class="sxs-lookup"><span data-stu-id="6db09-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="6db09-131">Verwenden der `StdCall` Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="6db09-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="6db09-132">In diesem Fall entleert der aufgerufene den Stapel.</span><span class="sxs-lookup"><span data-stu-id="6db09-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="6db09-133">Dies ist die Standardkonvention für das aufrufende nicht verwaltete Funktionen mit Plattformaufruf.</span><span class="sxs-lookup"><span data-stu-id="6db09-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="6db09-134">Verwenden der `ThisCall` Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="6db09-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="6db09-135">Der erste Parameter in diesem Fall ist die `this` Zeiger und wird im Register ECX gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6db09-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="6db09-136">Andere Parameter sind auf dem Stapel abgelegt.</span><span class="sxs-lookup"><span data-stu-id="6db09-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="6db09-137">Die `ThisCall` Aufrufkonvention wird zum Aufrufen von Methoden für Klassen, die aus einer nicht verwalteten DLL exportiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6db09-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="6db09-138">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="6db09-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="6db09-139">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="6db09-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6db09-140">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6db09-140">Requirements</span></span>  
 <span data-ttu-id="6db09-141">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6db09-141">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6db09-142">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6db09-142">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="6db09-143">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6db09-143">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6db09-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6db09-144">See also</span></span>

- [<span data-ttu-id="6db09-145">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="6db09-145">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
