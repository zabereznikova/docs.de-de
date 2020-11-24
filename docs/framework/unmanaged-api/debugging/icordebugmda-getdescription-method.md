---
title: ICorDebugMDA::GetDescription-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetDescription
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type:
- apiref
ms.openlocfilehash: cb1e0f2bc597b48496dc362c9d7a364421c68a87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681846"
---
# <a name="icordebugmdagetdescription-method"></a>ICorDebugMDA::GetDescription-Methode

Ruft eine Zeichenfolge ab, die die Beschreibung des von [ICorDebugMDA](icordebugmda-interface.md)dargestellten Assistenten für verwaltetes Debuggen (MDA) enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `cchName`  
 in Die Größe des Zeichen folgen Puffers, in dem die Beschreibung gespeichert wird.  
  
 `pcchName`  
 vorgenommen Ein Zeiger auf die Anzahl von Bytes, die im Zeichen folgen Puffer zurückgegeben werden.  
  
 `szName`  
 vorgenommen Ein Zeichen folgen Puffer, der die Beschreibung des MDA enthält.  
  
## <a name="remarks"></a>Hinweise  

 Die Zeichenfolge kann eine Länge von NULL aufweisen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugMDA-Schnittstelle](icordebugmda-interface.md)
- [Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
