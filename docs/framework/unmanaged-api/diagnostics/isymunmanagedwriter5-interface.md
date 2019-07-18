---
title: ISymUnmanagedWriter5-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6ed8c6e61c558a4bc9e3f92d559615ac93ecff8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962338"
---
# <a name="isymunmanagedwriter5-interface"></a>ISymUnmanagedWriter5-Schnittstelle
ISymUnmanagedWriter5-Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a>Methoden  
 Diese Schnittstelle enthält die folgenden Methoden:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CloseMapTokensToSourceSpans-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|Spezielle benutzerdefinierte Data-Abschnitt für Token-to-Source-Spanne, die Zuordnungsinformationen zu schließen. Nachdem sie geschlossen wurde, kann keine weiteren Zuordnungsinformationen hinzugefügt werden.|  
|[MapTokenToSourceSpan-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|Zuordnungen in die Zeile für die angegebene Quelle das angegebene Metadatentoken umfassen, in der angegebenen Quelldatei.<br /><br /> Muss aufgerufen werden, zwischen den Aufrufen [OpenMapTokensToSourceSpans-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) und [CloseMapTokensToSourceSpans-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).|  
|[OpenMapTokensToSourceSpans-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|Öffnen Sie einen spezielle benutzerdefinierte Daten im Abschnitt zum Ausgeben der Span-Token-to-Source-Zuordnungsinformationen in. Öffnen in diesem Abschnitt aus, wenn eine Methode bereits geöffnet ist, oder umgekehrt, ein Fehler wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter4-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
