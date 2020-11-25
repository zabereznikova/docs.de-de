---
title: ICorDebugRemoteTarget::GetHostName-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
ms.openlocfilehash: 3e946d8a27ec6b568b2f3c3633695c9f6795c938
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712052"
---
# <a name="icordebugremotetargetgethostname-method"></a>ICorDebugRemoteTarget::GetHostName-Methode

Gibt den vollqualifizierten Domänennamen oder die IPv4-Adresse des Remotedebugging-Zielcomputers zurück. IPV6 wird zurzeit nicht unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a>Parameter  

 `cchHostName`  
 [in] Die Größe des `szHostName`-Puffers in Zeichen. Wenn dieser Parameter 0 (Null) ist, muss `szHostName` NULL sein.  
  
 `pcchHostName`  
 [out] Die Anzahl der Zeichen einschließlich eines NULL-Terminators im Hostnamen oder in der IP-Adresse. Dieser Parameter kann NULL sein.  
  
 `szHostName`  
 [out] Puffer, der den Hostnamen oder die IP-Adresse enthält.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK  
 Der Hostname oder die IP-Adresse wurden erfolgreich zurückgegeben.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Fehler beim Zurückgeben des Hostnamens oder der IP-Adresse.  
  
## <a name="remarks"></a>Hinweise  

 Diese Methode wird vom Debugger-Writer implementiert. Er muss dem Paradigma für mehrere Aufrufe folgen: beim ersten Aufruf übergibt der Aufrufer NULL an `cchHostName` und und `szHostName` `pcchHostName` gibt die Größe des erforderlichen Puffers zurück. Beim zweiten Aufruf wird die Größe, die zuvor zurückgegeben wurde, an `cchHostName` übergeben, und ein entsprechend skalierten Puffer wird an `szHostName` übergeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 3,5 SP1  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugRemoteTarget-Schnittstelle](icordebugremotetarget-interface.md)
- [ICorDebug-Schnittstelle](icordebug-interface.md)
