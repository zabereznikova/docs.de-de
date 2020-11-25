---
title: ICorDebugMetaDataLocator::GetMetaData-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator.GetMetaData
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator::GetMetaData
helpviewer_keywords:
- ICorDebugMetaDataLocator::GetMetaData method [.NET Framework debugging]
- GetMetaData method, ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: f9b0ff22-54db-45eb-9cc3-508000a3141d
topic_type:
- apiref
ms.openlocfilehash: 63efb788d8bca84da94921371309704cc7b20ac4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710440"
---
# <a name="icordebugmetadatalocatorgetmetadata-method"></a>ICorDebugMetaDataLocator::GetMetaData-Methode

Fordert den Debugger auf, den vollständigen Pfad eines Moduls zurückzugeben, dessen Metadaten benötigt werden, um einen vom Debugger angeforderten Vorgang abzuschließen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMetaData(  
      [in] LPCWSTR wszImagePath,  
      [in] DWORD   dwImageTimeStamp,  
      [in] DWORD   dwImageSize,  
      [in] ULONG32 cchPathBuffer,  
      [out] ULONG32 * pcchPathBuffer,  
      [out, size_is(cchPathBuffer), length_is(*pcchPathBuffer)]  
               WCHAR wszPathBuffer[]  
      );  
```  
  
## <a name="parameters"></a>Parameter  

 `wszImagePath`  
 [in] Eine mit NULL endende Zeichenfolge, die den vollständigen Pfad zu der Datei darstellt. Wenn der vollständige Pfad nicht verfügbar ist, der Name und die Erweiterung der Datei (*Dateiname*.*Erweiterung*).  
  
 `dwImageTimeStamp`  
 [in] Der Zeitstempel aus den PE-Dateiheadern des Bilds. Dieser Parameter kann potenziell für einen Symbol Server ([SymSrv](/windows/desktop/debug/using-symsrv))-Lookup verwendet werden.  
  
 `dwImageSize`  
 [in] Die Bildgröße aus PE-Dateiheadern. Dieser Parameter kann potenziell für eine SymSrv-Suche verwendet werden.  
  
 `cchPathBuffer`  
 [in] Die Anzahl der Zeichen in `wszPathBuffer`.  
  
 `pcchPathBuffer`  
 [out] Die Anzahl der `WCHAR` in geschriebenen `wszPathBuffer`.  
  
 Wenn die Methode E_NOT_SUFFICIENT_BUFFER zurückgibt, ist die Anzahl der `WCHAR`s enthalten, die zum Speichern des Pfads erforderlich ist.  
  
 `wszPathBuffer`  
 [out] Ein Zeiger auf einen Puffer, in den der Debugger den vollständigen Pfad der Datei kopiert, die die angeforderten Metadaten enthält.  
  
 Das- `ofReadOnly` Flag aus der [CorOpenFlags](../metadata/coropenflags-enumeration.md) -Enumeration wird verwendet, um schreibgeschützten Zugriff auf die Metadaten in dieser Datei anzufordern.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen. Alle anderen Fehler-HRESULTs geben an, dass die Datei nicht abgerufen werden kann.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen. `wszPathBuffer` enthält den vollständigen Pfad zu der Datei und endet auf NULL.|  
|E_NOT_SUFFICIENT_BUFFER|Die aktuelle Größe von `wszPathBuffer` reicht nicht aus, um den vollständigen Pfad aufzunehmen. In diesem Fall enthält `pcchPathBuffer` die benötigte Anzahl von `WCHAR`s, einschließlich des abschließenden NULL-Zeichens, und `GetMetaData` wird ein zweites Mal mit der angeforderten Puffergröße aufgerufen.|  
  
## <a name="remarks"></a>Hinweise  

 Wenn `wszImagePath` einen vollständigen Pfad für ein Modul aus einem Speicherabbild enthält, gibt es den Pfad von dem Computer an, auf dem das Speicherabbild erfasst wurde. Die Datei ist an diesem Speicherort möglicherweise nicht vorhanden, oder es wird eine falsche Datei mit gleichem Namen in diesem Pfad gespeichert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugThread4-Schnittstelle](icordebugthread4-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
