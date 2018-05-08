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
ms.openlocfilehash: 7c130b92fd5114d067730da3b7cd138d98cf0577
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugappdomain3-interface"></a>ICorDebugAppDomain3-Schnittstelle
Stellt Methoden zum Abrufen von Informationen über die verwalteten Darstellungen des [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen, die derzeit in einer Anwendungsdomäne geladen. Diese Schnittstelle ist eine Erweiterung der ICorDebugAppDomain und ICorDebugAppDomain2-Schnittstellen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[Icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|Ruft einen Enumerator für alle zwischengespeicherten [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen.|  
|[Icordebugappdomain3:: Getcachedwinrttypesforiids](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|Ruft einen Enumerator ab, für die zwischengespeicherten [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen in einer Anwendungsdomäne basierend auf deren Schnittstellenbezeichner.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle von einem Debugger in Verbindung mit einem Funktionsaufruf für die Auswertung in verwendet werden sollen `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`. Wenn die Methode ruft die Schnittstellenbezeichner von unterstützt ab einem [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Server-Objekt, der Debugger kann in dieser Schnittstelle definierten Methoden verwenden, um sie verwaltete Typen zuzuordnen, die diese Schnittstellen entsprechen.  
  
 Führen Sie zum Abrufen einer Instanz dieser Schnittstelle `QueryInterface` auf eine Instanz der ICorDebugAppDomain oder ICorDebugAppDomain2-Schnittstelle.  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
