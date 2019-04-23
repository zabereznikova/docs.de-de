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
ms.openlocfilehash: 7c141ca9a8e1c74015883f45cb2eaa9183bb3d89
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177527"
---
# <a name="icordebugappdomain3-interface"></a>ICorDebugAppDomain3-Schnittstelle
Stellt Methoden zum Abrufen von Informationen über die verwaltete Darstellung der [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen, die derzeit in einer Anwendungsdomäne geladen. Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain und ICorDebugAppDomain2-Schnittstellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|Ruft einen Enumerator für alle zwischengespeicherten [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen.|  
|[ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|Ruft einen Enumerator ab, für die Zwischenspeicherung [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen in einer Anwendungsdomäne auf der Grundlage von deren Schnittstellenbezeichner.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle soll von einem Debugger in Verbindung mit einem Funktionsaufruf für die Auswertung zu verwendende `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`. Wenn die Methode ruft die Schnittstelle-IDs, die von unterstützt ab einem [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Server-Objekt, der Debugger können Sie die in der Schnittstelle definierten Methoden sie verwaltete Typen zuzuordnen, die diese Schnittstellen entsprechen.  
  
 Führen Sie zum Abrufen einer Instanz dieser Schnittstelle `QueryInterface` auf einer Instanz der ICorDebugAppDomain oder ICorDebugAppDomain2-Schnittstelle.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
