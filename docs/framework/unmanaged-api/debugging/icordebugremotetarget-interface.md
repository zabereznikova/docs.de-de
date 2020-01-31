---
title: ICorDebugRemoteTarget-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget
helpviewer_keywords:
- ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: bd9936a6-cc24-4869-8761-0988664464e6
topic_type:
- apiref
ms.openlocfilehash: bab6b7f683b5563cf362366dfb007f83caeee12d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791937"
---
# <a name="icordebugremotetarget-interface"></a>ICorDebugRemoteTarget-Schnittstelle
Stellt Methoden bereit, die es Entwicklern ermöglichen, Silverlight-basierte Anwendungen in der Umgebung der Common Language Runtime (CLR) zu debuggen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
interface ICorDebugRemoteTarget  : IUnknown  
{  
    HRESULT GetHostName (  
        [in]  ULONG32                    cchHostName,  
        [out] ULONG32*                   pcchHostName,  
        [out, size_is(cchHostName),  
              length_is(*pcchHostName)]  
                  WCHAR szHostName[]  
        );  
};  
```  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[ICorDebugRemoteTarget::GetHostName-Methode](icordebugremotetarget-gethostname-method.md)|Gibt den Hostnamen oder die IP-Adresse eines Remotecomputers zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Debuggen im gemischten Modus (verwalteter und nativer Code) wird unter Windows 95, Windows 98 und Windows Me sowie auf Nicht-x86-Plattformen (z. B. IA-64 und AMD64) nicht unterstützt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl  
  
 **Library:** : corguids. lib  
  
 **.NET Framework Versionen:** 3,5 SP1  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRemote-Schnittstelle](icordebugremote-interface.md)
- [ICorDebug-Schnittstelle](icordebug-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
