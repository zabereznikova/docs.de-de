---
title: ICLRDataTarget3::GetExceptionRecord-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type:
- apiref
ms.openlocfilehash: 037e216cb93e3aa6fce28966fc724498024abd52
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789058"
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a><span data-ttu-id="25659-102">ICLRDataTarget3::GetExceptionRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="25659-102">ICLRDataTarget3::GetExceptionRecord Method</span></span>
<span data-ttu-id="25659-103">Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Ausnahmedatensatz abzurufen, der dem Zielprozess zugordnet ist.</span><span class="sxs-lookup"><span data-stu-id="25659-103">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span> <span data-ttu-id="25659-104">Bei einem dumpziel wäre dies z. b. äquivalent zu dem Ausnahme Daten Satz, der über das `ExceptionParam`-Argument an die [minidumpschreitedump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) -Funktion in der Windows-Debug-Hilfe-Bibliothek (dbghelp) weitergegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="25659-104">For example, for a dump target, this would be equivalent to the exception record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25659-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="25659-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25659-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="25659-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="25659-107">[in] Die Eingabepuffergröße, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="25659-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="25659-108">Dies muss `sizeof(`[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception)`)`identisch sein.</span><span class="sxs-lookup"><span data-stu-id="25659-108">This must be equal to `sizeof(`[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception)`)`.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="25659-109">[out] Ein Zeiger auf ein `ULONG32`-Typ, der die Anzahl von Bytes empfängt, die tatsächlich in den Puffer geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="25659-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="25659-110">[out] Ein Zeiger zu einem Arbeitsspeicherpuffer, der eine Kopie des Ausnahmedatensatzes empfängt.</span><span class="sxs-lookup"><span data-stu-id="25659-110">[out] A pointer to a memory buffer that receives a copy of the exception record.</span></span> <span data-ttu-id="25659-111">Der Ausnahme Daten Satz wird als [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) -Typ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="25659-111">The exception record is returned as a [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25659-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="25659-112">Return Value</span></span>  
 <span data-ttu-id="25659-113">Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="25659-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="25659-114">Zu den `HRESULT`-Codes können u. a. folgende Codes gehören:</span><span class="sxs-lookup"><span data-stu-id="25659-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="25659-115">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="25659-115">Return code</span></span>|<span data-ttu-id="25659-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25659-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="25659-117">Methode war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="25659-117">Method succeeded.</span></span> <span data-ttu-id="25659-118">Der Ausnahmedatensatz ist in den Ausgabepuffer kopiert worden.</span><span class="sxs-lookup"><span data-stu-id="25659-118">The exception record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="25659-119">Kein Ausnahmedatensatz ist dem Ziel zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="25659-119">No exception record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="25659-120">Die Eingabepuffergröße ist ungleich `sizeof(MINIDUMP_EXCEPTION)`.</span><span class="sxs-lookup"><span data-stu-id="25659-120">The input buffer size is not equal to `sizeof(MINIDUMP_EXCEPTION)`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25659-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25659-121">Remarks</span></span>  
 <span data-ttu-id="25659-122">[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) ist eine Struktur, die in "dbghelp. h" und in "Imagehlp. h" im Windows SDK definiert ist.</span><span class="sxs-lookup"><span data-stu-id="25659-122">[MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) is a structure defined in dbghelp.h and imagehlp.h in the Windows SDK.</span></span>  
  
 <span data-ttu-id="25659-123">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="25659-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25659-124">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25659-124">Requirements</span></span>  
 <span data-ttu-id="25659-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25659-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25659-126">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="25659-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="25659-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25659-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25659-128">**.NET Framework Versionen:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="25659-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25659-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25659-129">See also</span></span>

- [<span data-ttu-id="25659-130">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25659-130">ICLRDataTarget3 Interface</span></span>](iclrdatatarget3-interface.md)
- [<span data-ttu-id="25659-131">GetExceptionContextRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="25659-131">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="25659-132">GetExceptionThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="25659-132">GetExceptionThreadID Method</span></span>](iclrdatatarget3-getexceptionthreadid-method.md)
