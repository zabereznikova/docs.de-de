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
ms.openlocfilehash: d55fd042cf478c6b3e39298f84f5a931bb346a74
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585444"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a>ICLRDataTarget3::GetExceptionContextRecord-Methode
Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Kontextdatensatz abzurufen, der dem Zielprozess zugordnet ist. Z. B. bei einem Sicherungsziel entspräche dem Kontextdatensatz, der über übergeben die `ExceptionParam` Argument für die [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) -Funktion in der Windows Debug-Hilfe-Bibliothek (DbgHelp).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `bufferSize`  
 [in] Die Eingabepuffergröße, in Bytes. Diese muss groß genug sein, um den Kontextdatensatz aufzunehmen.  
  
 `bufferUsed`  
 [out] Ein Zeiger auf ein `ULONG32`-Typ, der die Anzahl von Bytes empfängt, die tatsächlich in den Puffer geschrieben werden.  
  
 `buffer`  
 [out] Ein Zeiger zu einem Arbeitsspeicherpuffer, der eine Kopie des Kontextdatensatzes empfängt. Der Ausnahmedatensatz wird zurückgegeben, als eine [Kontext](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) Typ.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler. Zu den `HRESULT`-Codes können u. a. folgende Codes gehören:  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|`S_OK`|Methode war erfolgreich. Der Kontextdatensatz ist in den Ausgabepuffer kopiert worden.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Kein Kontextdatensatz ist dem Ziel zugeordnet.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|Die Eingabepuffergröße ist nicht groß genug, um den Kontextdatensatz aufzunehmen.|  
  
## <a name="remarks"></a>Hinweise  
 [Kontext](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) ist eine plattformspezifische Struktur, die definiert, die in Headern, die vom Windows SDK bereitgestellt werden.  
  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl, ClrData.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICLRDataTarget3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [GetExceptionRecord-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
- [GetExceptionThreadID-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
