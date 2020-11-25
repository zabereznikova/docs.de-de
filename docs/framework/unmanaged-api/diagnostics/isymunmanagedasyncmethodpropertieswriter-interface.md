---
title: ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: 779b737da43f61d1023a0a640dce936e11c4704c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707034"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a>ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle

Ermöglicht das definieren Optionaler Async-Methoden Informationen für jedes Methoden Symbol. Immer mit einer geöffneten Methode verwenden; Das heißt, zwischen Aufrufen der [OpenMethod-Methode](isymunmanagedwriter-openmethod-method.md) und der [CloseMethod-Methode](isymunmanagedwriter-closemethod-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a>Methoden  

 Diese Schnittstelle enthält die folgenden Methoden:  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[DefineAsyncStepInfo-Methode](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|Definieren Sie eine Gruppe von asynchronen warte Vorgängen in der aktuellen Methode.<br /><br /> Jeder yield-Offset entspricht der Return-Anweisung, die eine mögliche Rendite identifiziert. Jedes `breakpointMethod` / `breakpointOffset` paar gibt an, wo der asynchrone Vorgang fortgesetzt wird. er kann sich in einer anderen Methode befinden.|  
|[DefineCatchHandlerILOffset-Methode](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|Legt den IL-Offset für den vom Compiler generierten catch-Handler fest, der eine Async-Methode umschließt.<br /><br /> Der IL-Offset des generierten catch wird vom Debugger verwendet, um den catch so zu behandeln, als ob es sich um Nichtbenutzer Code handelt, auch wenn er in einer Benutzercode Methode auftreten kann. Insbesondere wird **er als Reaktion auf ein Ereignis** vom Typ "Ereignis Ereignis Ereignis-Ausnahme" verwendet.|  
|[DefineKickoffMethod-Methode](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|Legt die Anfangs Methode fest, die den asynchronen Vorgang initiiert.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
