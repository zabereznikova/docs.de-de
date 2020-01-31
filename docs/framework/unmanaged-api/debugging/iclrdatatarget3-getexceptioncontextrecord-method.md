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
ms.openlocfilehash: aed301fa136ff3d45269c82b46e4cad699074874
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785242"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a>ICLRDataTarget3::GetExceptionContextRecord-Methode
Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Kontextdatensatz abzurufen, der dem Zielprozess zugordnet ist. Bei einem dumpziel wäre dies z. b. Äquivalent zum Kontext Daten Satz, der über das `ExceptionParam`-Argument an die [minidumpschreitedump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) -Funktion in der Windows-Debug-Hilfe-Bibliothek (dbghelp) weitergeleitet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `bufferSize`  
 [in] Die Eingabepuffergröße, in Bytes. Diese muss groß genug sein, um den Kontextdatensatz aufzunehmen.  
  
 `bufferUsed`  
 [out] Ein Zeiger auf ein `ULONG32`-Typ, der die Anzahl von Bytes empfängt, die tatsächlich in den Puffer geschrieben werden.  
  
 `buffer`  
 [out] Ein Zeiger zu einem Arbeitsspeicherpuffer, der eine Kopie des Kontextdatensatzes empfängt. Der Ausnahme Daten Satz [wird als Kontexttyp](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) zurückgegeben.  
  
## <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler. Zu den `HRESULT`-Codes können u. a. folgende Codes gehören:  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|`S_OK`|Methode war erfolgreich. Der Kontextdatensatz ist in den Ausgabepuffer kopiert worden.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Kein Kontextdatensatz ist dem Ziel zugeordnet.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|Die Eingabepuffergröße ist nicht groß genug, um den Kontextdatensatz aufzunehmen.|  
  
## <a name="remarks"></a>Hinweise  
 [Context](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) ist eine plattformspezifische Struktur, die in Headern definiert ist, die vom Windows SDK bereitgestellt werden.  
  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICLRDataTarget3-Schnittstelle](iclrdatatarget3-interface.md)
- [GetExceptionRecord-Methode](iclrdatatarget3-getexceptionrecord-method.md)
- [GetExceptionThreadID-Methode](iclrdatatarget3-getexceptionthreadid-method.md)
