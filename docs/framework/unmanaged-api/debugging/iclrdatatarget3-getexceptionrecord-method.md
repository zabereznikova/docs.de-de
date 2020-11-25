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
ms.openlocfilehash: 8f6eaa6ad310e9a01b2307bff091b670c3e1d6cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723609"
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a>ICLRDataTarget3::GetExceptionRecord-Methode

Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Ausnahmedatensatz abzurufen, der dem Zielprozess zugordnet ist. Bei einem dumpziel wäre dies z. b. äquivalent zu dem Ausnahme Daten Satz, der über das- `ExceptionParam` Argument an die [minidumpschreitedump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) -Funktion in der Windows-Debug-Hilfe-Bibliothek (dbghelp) weitergeleitet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `bufferSize`  
 [in] Die Eingabepuffergröße, in Bytes. Dieser muss `sizeof(` [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception)entsprechen `)` .  
  
 `bufferUsed`  
 [out] Ein Zeiger auf ein `ULONG32`-Typ, der die Anzahl von Bytes empfängt, die tatsächlich in den Puffer geschrieben werden.  
  
 `buffer`  
 [out] Ein Zeiger zu einem Arbeitsspeicherpuffer, der eine Kopie des Ausnahmedatensatzes empfängt. Der Ausnahme Daten Satz wird als [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) -Typ zurückgegeben.  
  
## <a name="return-value"></a>Rückgabewert  

 Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler. Zu den `HRESULT`-Codes können u. a. folgende Codes gehören:  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|`S_OK`|Methode war erfolgreich. Der Ausnahmedatensatz ist in den Ausgabepuffer kopiert worden.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Kein Ausnahmedatensatz ist dem Ziel zugeordnet.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|Die Eingabepuffergröße ist ungleich `sizeof(MINIDUMP_EXCEPTION)`.|  
  
## <a name="remarks"></a>Hinweise  

 [MINIDUMP_EXCEPTION](/windows/win32/api/minidumpapiset/ns-minidumpapiset-minidump_exception) ist eine Struktur, die in "dbghelp. h" und in "Imagehlp. h" im Windows SDK definiert ist.  
  
 Diese Methode wird vom Writer der Debuganwendung implementiert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Clrdata. idl, Clrdata. h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICLRDataTarget3-Schnittstelle](iclrdatatarget3-interface.md)
- [GetExceptionContextRecord-Methode](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [GetExceptionThreadID-Methode](iclrdatatarget3-getexceptionthreadid-method.md)
