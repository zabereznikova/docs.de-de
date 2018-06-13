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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b07318406268023e2d66259b2cb68750d64613e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408163"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a><span data-ttu-id="41d99-102">ICLRDataTarget3::GetExceptionContextRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="41d99-102">ICLRDataTarget3::GetExceptionContextRecord Method</span></span>
<span data-ttu-id="41d99-103">Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Kontextdatensatz abzurufen, der dem Zielprozess zugordnet ist.</span><span class="sxs-lookup"><span data-stu-id="41d99-103">Called by the common language runtime (CLR) data access services to retrieve the context record associated with the target process.</span></span> <span data-ttu-id="41d99-104">Z. B. bei einem, wäre dies entspricht dem Kontextdatensatz, der über übergeben der `ExceptionParam` Argument an die [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360\(v=vs.85\).aspx) -Funktion in der Windows Debug-Hilfe-Bibliothek (DbgHelp).</span><span class="sxs-lookup"><span data-stu-id="41d99-104">For example, for a dump target, this would be equivalent to the context record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360\(v=vs.85\).aspx) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41d99-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="41d99-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41d99-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="41d99-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="41d99-107">[in] Die Eingabepuffergröße, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="41d99-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="41d99-108">Diese muss groß genug sein, um den Kontextdatensatz aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="41d99-108">This must be large enough to accommodate the context record.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="41d99-109">[out] Ein Zeiger auf ein `ULONG32`-Typ, der die Anzahl von Bytes empfängt, die tatsächlich in den Puffer geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="41d99-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="41d99-110">[out] Ein Zeiger zu einem Arbeitsspeicherpuffer, der eine Kopie des Kontextdatensatzes empfängt.</span><span class="sxs-lookup"><span data-stu-id="41d99-110">[out] A pointer to a memory buffer that receives a copy of the context record.</span></span> <span data-ttu-id="41d99-111">Der Ausnahmedatensatz wird zurückgegeben, als eine [Kontext](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) Typ.</span><span class="sxs-lookup"><span data-stu-id="41d99-111">The exception record is returned as a [CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="41d99-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="41d99-112">Return Value</span></span>  
 <span data-ttu-id="41d99-113">Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="41d99-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="41d99-114">Zu den `HRESULT`-Codes können u. a. folgende Codes gehören:</span><span class="sxs-lookup"><span data-stu-id="41d99-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="41d99-115">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="41d99-115">Return code</span></span>|<span data-ttu-id="41d99-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41d99-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="41d99-117">Methode war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="41d99-117">Method succeeded.</span></span> <span data-ttu-id="41d99-118">Der Kontextdatensatz ist in den Ausgabepuffer kopiert worden.</span><span class="sxs-lookup"><span data-stu-id="41d99-118">The context record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="41d99-119">Kein Kontextdatensatz ist dem Ziel zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="41d99-119">No context record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="41d99-120">Die Eingabepuffergröße ist nicht groß genug, um den Kontextdatensatz aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="41d99-120">The input buffer size is not large enough to accommodate the context record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41d99-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41d99-121">Remarks</span></span>  
 <span data-ttu-id="41d99-122">[Kontext](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) ist eine plattformspezifische-Struktur, die in das Windows SDK-Headern definiert.</span><span class="sxs-lookup"><span data-stu-id="41d99-122">[CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) is a platform-specific structure defined in headers provided by the Windows SDK.</span></span>  
  
 <span data-ttu-id="41d99-123">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="41d99-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41d99-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41d99-124">Requirements</span></span>  
 <span data-ttu-id="41d99-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41d99-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41d99-126">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="41d99-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="41d99-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41d99-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41d99-128">**.NET Framework-Versionen:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41d99-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d99-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41d99-129">See Also</span></span>  
 [<span data-ttu-id="41d99-130">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41d99-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="41d99-131">GetExceptionRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="41d99-131">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)  
 [<span data-ttu-id="41d99-132">GetExceptionThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="41d99-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
