---
title: ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d83270d0e7f5dabff8402f5f81dae20d4457d147
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604247"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a>ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle
Können Sie Informationen zu optionalen Async-Methode für jedes methodensymbol definieren. Verwenden Sie immer mit einer geöffneten Methode; d. h. zwischen den Aufrufen der [OpenMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) und [CloseMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a>Methoden  
 Diese Schnittstelle enthält die folgenden Methoden:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DefineAsyncStepInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|Definieren Sie eine Gruppe von Async "await" Vorgänge in der aktuellen Methode.<br /><br /> Jede Offset "yield" entspricht einem "await" return-Anweisung, Identifizieren einer potenziellen "yield". Jede `breakpointMethod` / `breakpointOffset` Paar identifiziert, in dem der asynchrone Vorgang fortgesetzt wird; es kann sein, in einer anderen Methode.|  
|[DefineCatchHandlerILOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|Legt fest, die IL-offset für den vom Compiler generierter Catch-Handler, der eine asynchrone Methode umschließt.<br /><br /> Der IL-Offset des generierten Catch wird vom Debugger zum Catch als handele es sich um nicht-benutzerseitiger Code verarbeiten kann, obwohl es in einer Code-Methode für Benutzer auftreten kann. Es wird insbesondere verwendet, als Reaktion auf eine **CatchHandlerFound** Ausnahmeereignisses.|  
|[DefineKickoffMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|Legt die Start-Methode, die den asynchronen Vorgang initiiert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
