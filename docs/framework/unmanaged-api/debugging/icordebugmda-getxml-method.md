---
title: ICorDebugMDA::GetXML-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
ms.openlocfilehash: f80bdffbf5c0ba39980bd27c6e89a368547340c0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129808"
---
# <a name="icordebugmdagetxml-method"></a>ICorDebugMDA::GetXML-Methode
Ruft den vollständigen XML-Stream ab, der dem von [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)dargestellten Assistenten für verwaltetes Debuggen (MDA) zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cchName`  
 [in] Die Größe des `szName`-Arrays.  
  
 `pcchName`  
 vorgenommen Ein Zeiger auf die Länge des XML-Streams.  
  
 `szName`  
 vorgenommen Ein Array, in dem der XML-Stream gespeichert werden soll. Das Array ist möglicherweise leer.  
  
## <a name="remarks"></a>Hinweise  
 Abhängig von der Größe des zugeordneten XML-Streams kann sich die `GetXML`-Methode potenziell auf die Leistung auswirken.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugMDA-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
