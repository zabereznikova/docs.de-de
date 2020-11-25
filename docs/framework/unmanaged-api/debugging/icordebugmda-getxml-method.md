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
ms.openlocfilehash: 9a088c7e4e9c72c8247ccdd384bc724587210c37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710869"
---
# <a name="icordebugmdagetxml-method"></a>ICorDebugMDA::GetXML-Methode

Ruft den vollständigen XML-Stream ab, der dem von [ICorDebugMDA](icordebugmda-interface.md)dargestellten Assistenten für verwaltetes Debuggen (MDA) zugeordnet ist.  
  
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

 `GetXML`Abhängig von der Größe des zugeordneten XML-Streams kann sich die-Methode potenziell auf die Leistung auswirken.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugMDA-Schnittstelle](icordebugmda-interface.md)
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
