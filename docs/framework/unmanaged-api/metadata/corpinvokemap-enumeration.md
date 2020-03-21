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
ms.openlocfilehash: 8216dc3030b18428ab52fbf8385d392f81057aa0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176148"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="604b2-102">CorPinvokeMap-Enumeration</span><span class="sxs-lookup"><span data-stu-id="604b2-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="604b2-103">Gibt Optionen für einen PInvoke-Aufruf an.</span><span class="sxs-lookup"><span data-stu-id="604b2-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="604b2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="604b2-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="604b2-105">Members</span><span class="sxs-lookup"><span data-stu-id="604b2-105">Members</span></span>  
  
|<span data-ttu-id="604b2-106">Member</span><span class="sxs-lookup"><span data-stu-id="604b2-106">Member</span></span>|<span data-ttu-id="604b2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="604b2-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="604b2-108">Verwenden Sie jeden Mitgliedsnamen wie angegeben.</span><span class="sxs-lookup"><span data-stu-id="604b2-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="604b2-109">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="604b2-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="604b2-110">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="604b2-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="604b2-111">Marshallt Zeichenfolgen als Mehrfachbyte-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="604b2-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="604b2-112">Marshallt Zeichenfolgen als 2-Byte-Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="604b2-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="604b2-113">Marshallt Zeichenfolgen automatisch entsprechend dem Zielbetriebssystem.</span><span class="sxs-lookup"><span data-stu-id="604b2-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="604b2-114">Der Standardwert ist Unicode unter Windows NT, Windows 2000, Windows XP und der Windows Server 2003-Produktreihe. Der Standardwert ist ANSI unter Windows 98 und Windows Me.</span><span class="sxs-lookup"><span data-stu-id="604b2-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="604b2-115">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="604b2-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="604b2-116">Führen Sie die optimale Zuordnung von Unicode-Zeichen durch, denen eine exakte Übereinstimmung im ANSI-Zeichensatz fehlt.</span><span class="sxs-lookup"><span data-stu-id="604b2-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="604b2-117">Führen Sie keine optimale Zuordnung von Unicode-Zeichen durch.</span><span class="sxs-lookup"><span data-stu-id="604b2-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="604b2-118">In diesem Fall werden alle nicht bespielbaren Zeichen durch ein '?' ersetzt.</span><span class="sxs-lookup"><span data-stu-id="604b2-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="604b2-119">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="604b2-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="604b2-120">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="604b2-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="604b2-121">Auslösen einer Ausnahme, wenn der Interop-Marshaller auf ein nicht zu treffendes Zeichen trifft.</span><span class="sxs-lookup"><span data-stu-id="604b2-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="604b2-122">Werfen Sie keine Ausnahme aus, wenn der Interop-Marshaller auf ein nicht bewertes Zeichen trifft.</span><span class="sxs-lookup"><span data-stu-id="604b2-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="604b2-123">Reserved</span><span class="sxs-lookup"><span data-stu-id="604b2-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="604b2-124">Erlauben Sie dem Angerufenen, die `SetLastError` Win32-Funktion aufzurufen, bevor er von der attributierten Methode zurückkehrt.</span><span class="sxs-lookup"><span data-stu-id="604b2-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="604b2-125">Reserved</span><span class="sxs-lookup"><span data-stu-id="604b2-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="604b2-126">Verwenden Sie die Standardplattformaufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="604b2-126">Use the default platform calling convention.</span></span> <span data-ttu-id="604b2-127">Unter Windows ist `StdCall` z. B. der Standardwert `Cdecl`und unter Windows CE .NET ist es .</span><span class="sxs-lookup"><span data-stu-id="604b2-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="604b2-128">Verwenden `Cdecl` Sie die Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="604b2-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="604b2-129">In diesem Fall reinigt der Aufrufer den Stapel.</span><span class="sxs-lookup"><span data-stu-id="604b2-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="604b2-130">Dadurch werden Aufruffunktionen mit `varargs` (d. h. Funktionen, die eine variable Anzahl von Parametern akzeptieren) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="604b2-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="604b2-131">Verwenden `StdCall` Sie die Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="604b2-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="604b2-132">In diesem Fall reinigt der Angerufene den Stapel.</span><span class="sxs-lookup"><span data-stu-id="604b2-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="604b2-133">Dies ist die Standardkonvention für das Aufrufen nicht verwalteter Funktionen mit Plattformaufruf.</span><span class="sxs-lookup"><span data-stu-id="604b2-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="604b2-134">Verwenden `ThisCall` Sie die Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="604b2-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="604b2-135">In diesem Fall ist der `this` erste Parameter der Zeiger und wird im Register ECX gespeichert.</span><span class="sxs-lookup"><span data-stu-id="604b2-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="604b2-136">Weitere Parameter werden in den Stapel verschoben.</span><span class="sxs-lookup"><span data-stu-id="604b2-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="604b2-137">Die `ThisCall` aufrufende Konvention wird verwendet, um Methoden für Klassen aufzurufen, die aus einer nicht verwalteten DLL exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="604b2-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="604b2-138">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="604b2-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="604b2-139">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="604b2-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="604b2-140">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="604b2-140">Requirements</span></span>  
 <span data-ttu-id="604b2-141">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="604b2-141">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="604b2-142">**Kopfzeile:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="604b2-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="604b2-143">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="604b2-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604b2-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="604b2-144">See also</span></span>

- [<span data-ttu-id="604b2-145">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="604b2-145">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
