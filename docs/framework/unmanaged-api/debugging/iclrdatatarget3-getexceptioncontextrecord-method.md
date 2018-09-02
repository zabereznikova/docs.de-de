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
ms.openlocfilehash: 72c45e821a59c1e910b5c8422df02978046eb56b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425223"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a><span data-ttu-id="7be7f-102">ICLRDataTarget3::GetExceptionContextRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="7be7f-102">ICLRDataTarget3::GetExceptionContextRecord Method</span></span>
<span data-ttu-id="7be7f-103">Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Kontextdatensatz abzurufen, der dem Zielprozess zugordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7be7f-103">Called by the common language runtime (CLR) data access services to retrieve the context record associated with the target process.</span></span> <span data-ttu-id="7be7f-104">Z. B. bei einem Sicherungsziel entspräche dem Kontextdatensatz, der über übergeben die `ExceptionParam` Argument für die [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) -Funktion in der Windows Debug-Hilfe-Bibliothek (DbgHelp).</span><span class="sxs-lookup"><span data-stu-id="7be7f-104">For example, for a dump target, this would be equivalent to the context record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7be7f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7be7f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7be7f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7be7f-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="7be7f-107">[in] Die Eingabepuffergröße, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="7be7f-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="7be7f-108">Diese muss groß genug sein, um den Kontextdatensatz aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="7be7f-108">This must be large enough to accommodate the context record.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="7be7f-109">[out] Ein Zeiger auf ein `ULONG32`-Typ, der die Anzahl von Bytes empfängt, die tatsächlich in den Puffer geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7be7f-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="7be7f-110">[out] Ein Zeiger zu einem Arbeitsspeicherpuffer, der eine Kopie des Kontextdatensatzes empfängt.</span><span class="sxs-lookup"><span data-stu-id="7be7f-110">[out] A pointer to a memory buffer that receives a copy of the context record.</span></span> <span data-ttu-id="7be7f-111">Der Ausnahmedatensatz wird zurückgegeben, als eine [Kontext](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) Typ.</span><span class="sxs-lookup"><span data-stu-id="7be7f-111">The exception record is returned as a [CONTEXT](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7be7f-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7be7f-112">Return Value</span></span>  
 <span data-ttu-id="7be7f-113">Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="7be7f-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="7be7f-114">Zu den `HRESULT`-Codes können u. a. folgende Codes gehören:</span><span class="sxs-lookup"><span data-stu-id="7be7f-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="7be7f-115">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="7be7f-115">Return code</span></span>|<span data-ttu-id="7be7f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7be7f-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="7be7f-117">Methode war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="7be7f-117">Method succeeded.</span></span> <span data-ttu-id="7be7f-118">Der Kontextdatensatz ist in den Ausgabepuffer kopiert worden.</span><span class="sxs-lookup"><span data-stu-id="7be7f-118">The context record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="7be7f-119">Kein Kontextdatensatz ist dem Ziel zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7be7f-119">No context record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="7be7f-120">Die Eingabepuffergröße ist nicht groß genug, um den Kontextdatensatz aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="7be7f-120">The input buffer size is not large enough to accommodate the context record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7be7f-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7be7f-121">Remarks</span></span>  
 <span data-ttu-id="7be7f-122">[Kontext](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) ist eine plattformspezifische Struktur, die definiert, die in Headern, die vom Windows SDK bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7be7f-122">[CONTEXT](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) is a platform-specific structure defined in headers provided by the Windows SDK.</span></span>  
  
 <span data-ttu-id="7be7f-123">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="7be7f-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7be7f-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7be7f-124">Requirements</span></span>  
 <span data-ttu-id="7be7f-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7be7f-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7be7f-126">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="7be7f-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7be7f-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7be7f-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7be7f-128">**.NET Framework-Versionen:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7be7f-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7be7f-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7be7f-129">See Also</span></span>  
 [<span data-ttu-id="7be7f-130">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7be7f-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="7be7f-131">GetExceptionRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="7be7f-131">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)  
 [<span data-ttu-id="7be7f-132">GetExceptionThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="7be7f-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
