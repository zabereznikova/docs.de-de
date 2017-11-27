---
title: ICorDebugRemoteTarget::GetHostName-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemoteTarget.GetHostName
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2af5d75145b9fdd2d370b76f798c5e350d8bec50
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugremotetargetgethostname-method"></a>ICorDebugRemoteTarget::GetHostName-Methode
Gibt den vollqualifizierten Domänennamen oder die IPv4-Adresse des Remotedebugging-Zielcomputers zurück. IPV6 wird zurzeit nicht unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
#### <a name="parameters"></a>Parameter  
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
 Diese Methode wird vom Debugger-Writer implementiert. Sie muss dem Paradigma für mehrere Aufrufe entsprechen: Beim ersten Aufruf übergibt der Aufrufer sowohl `cchHostName` als auch `szHostName`, und `pcchHostName` gibt die Größe des erforderlichen Puffers zurück. Beim zweiten Aufruf wird die Größe, die zuvor zurückgegeben wurde, an `cchHostName` übergeben, und ein entsprechend skalierten Puffer wird an `szHostName` übergeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 3.5 SP1  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugRemoteTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
