---
title: ICorDebugAppDomain3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 256fd900fa73948b4ca42ac6b6f21f145effc461
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025892"
---
# <a name="icordebugappdomain3-interface"></a>ICorDebugAppDomain3-Schnittstelle
Stellt Methoden zum Abrufen von Informationen über die verwaltete Darstellung der Windows-Runtime-Typen, die derzeit in einer Anwendungsdomäne geladen. Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain und ICorDebugAppDomain2-Schnittstellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|Ruft einen Enumerator für alle zwischengespeicherten Windows-Runtime-Typen ab.|  
|[ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|Ruft einen Enumerator für zwischengespeicherte Windows-Runtime-Typen in einer Anwendungsdomäne, basierend auf ihren Schnittstellenbezeichner ab.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle soll von einem Debugger in Verbindung mit einem Funktionsaufruf für die Auswertung zu verwendende `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`. Wenn die Methode die Schnittstelle-IDs, die von einem Windows-Runtime-Server-Objekt unterstützt abruft, kann der Debugger die in der Schnittstelle definierten Methoden verwenden, sie verwaltete Typen zuzuordnen, die diese Schnittstellen entsprechen.  
  
 Führen Sie zum Abrufen einer Instanz dieser Schnittstelle `QueryInterface` auf einer Instanz der ICorDebugAppDomain oder ICorDebugAppDomain2-Schnittstelle.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Windows-Runtime  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
