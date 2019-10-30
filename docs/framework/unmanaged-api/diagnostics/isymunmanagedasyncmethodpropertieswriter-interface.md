---
title: ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: db065357e22ac576600a3ca61dda0882b9206a86
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129155"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a>ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle
Ermöglicht das definieren Optionaler Async-Methoden Informationen für jedes Methoden Symbol. Immer mit einer geöffneten Methode verwenden; Das heißt, zwischen Aufrufen der [OpenMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) und der [CloseMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a>Methoden  
 Diese Schnittstelle enthält die folgenden Methoden:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DefineAsyncStepInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|Definieren Sie eine Gruppe von asynchronen warte Vorgängen in der aktuellen Methode.<br /><br /> Jeder yield-Offset entspricht der Return-Anweisung, die eine mögliche Rendite identifiziert. Jede `breakpointMethod`/`breakpointOffset` Paars identifiziert, wo der asynchrone Vorgang fortgesetzt wird. Sie kann sich in einer anderen Methode befinden.|  
|[DefineCatchHandlerILOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|Legt den IL-Offset für den vom Compiler generierten catch-Handler fest, der eine Async-Methode umschließt.<br /><br /> Der IL-Offset des generierten catch wird vom Debugger verwendet, um den catch so zu behandeln, als ob es sich um Nichtbenutzer Code handelt, auch wenn er in einer Benutzercode Methode auftreten kann. Insbesondere wird **er als Reaktion auf ein Ereignis** vom Typ "Ereignis Ereignis Ereignis-Ausnahme" verwendet.|  
|[DefineKickoffMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|Legt die Anfangs Methode fest, die den asynchronen Vorgang initiiert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
