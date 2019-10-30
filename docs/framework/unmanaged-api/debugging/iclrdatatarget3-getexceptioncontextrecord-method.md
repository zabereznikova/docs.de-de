---
title: ICLRDataTarget3::GetExceptionContextRecord-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetContextRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type:
- apiref
ms.openlocfilehash: 5a090b7c4801e6b2baf56f1d80e7e52f2aaa9293
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73112299"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a><span data-ttu-id="383b4-102">ICLRDataTarget3::GetExceptionContextRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="383b4-102">ICLRDataTarget3::GetExceptionContextRecord Method</span></span>
<span data-ttu-id="383b4-103">Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Kontextdatensatz abzurufen, der dem Zielprozess zugordnet ist.</span><span class="sxs-lookup"><span data-stu-id="383b4-103">Called by the common language runtime (CLR) data access services to retrieve the context record associated with the target process.</span></span> <span data-ttu-id="383b4-104">Bei einem dumpziel wäre dies z. b. Äquivalent zum Kontext Daten Satz, der über das `ExceptionParam`-Argument an die [minidumpschreitedump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) -Funktion in der Windows-Debug-Hilfe-Bibliothek (dbghelp) weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="383b4-104">For example, for a dump target, this would be equivalent to the context record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="383b4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="383b4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="383b4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="383b4-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="383b4-107">[in] Die Eingabepuffergröße, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="383b4-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="383b4-108">Diese muss groß genug sein, um den Kontextdatensatz aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="383b4-108">This must be large enough to accommodate the context record.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="383b4-109">[out] Ein Zeiger auf ein `ULONG32`-Typ, der die Anzahl von Bytes empfängt, die tatsächlich in den Puffer geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="383b4-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="383b4-110">[out] Ein Zeiger zu einem Arbeitsspeicherpuffer, der eine Kopie des Kontextdatensatzes empfängt.</span><span class="sxs-lookup"><span data-stu-id="383b4-110">[out] A pointer to a memory buffer that receives a copy of the context record.</span></span> <span data-ttu-id="383b4-111">Der Ausnahme Daten Satz [wird als Kontexttyp](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="383b4-111">The exception record is returned as a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="383b4-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="383b4-112">Return Value</span></span>  
 <span data-ttu-id="383b4-113">Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="383b4-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="383b4-114">Zu den `HRESULT`-Codes können u. a. folgende Codes gehören:</span><span class="sxs-lookup"><span data-stu-id="383b4-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="383b4-115">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="383b4-115">Return code</span></span>|<span data-ttu-id="383b4-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="383b4-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="383b4-117">Methode war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="383b4-117">Method succeeded.</span></span> <span data-ttu-id="383b4-118">Der Kontextdatensatz ist in den Ausgabepuffer kopiert worden.</span><span class="sxs-lookup"><span data-stu-id="383b4-118">The context record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="383b4-119">Kein Kontextdatensatz ist dem Ziel zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="383b4-119">No context record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="383b4-120">Die Eingabepuffergröße ist nicht groß genug, um den Kontextdatensatz aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="383b4-120">The input buffer size is not large enough to accommodate the context record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="383b4-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="383b4-121">Remarks</span></span>  
 <span data-ttu-id="383b4-122">[Context](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) ist eine plattformspezifische Struktur, die in Headern definiert ist, die vom Windows SDK bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="383b4-122">[CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) is a platform-specific structure defined in headers provided by the Windows SDK.</span></span>  
  
 <span data-ttu-id="383b4-123">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="383b4-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="383b4-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="383b4-124">Requirements</span></span>  
 <span data-ttu-id="383b4-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="383b4-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="383b4-126">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="383b4-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="383b4-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="383b4-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="383b4-128">**.NET Framework-Versionen:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="383b4-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="383b4-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="383b4-129">See also</span></span>

- [<span data-ttu-id="383b4-130">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="383b4-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="383b4-131">GetExceptionRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="383b4-131">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
- [<span data-ttu-id="383b4-132">GetExceptionThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="383b4-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
