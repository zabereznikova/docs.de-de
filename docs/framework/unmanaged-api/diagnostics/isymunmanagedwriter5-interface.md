---
title: ISymUnmanagedWriter5-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: d9204457b71b670e1c96ed228ad11116bdf41fe6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493577"
---
# <a name="isymunmanagedwriter5-interface"></a>ISymUnmanagedWriter5-Schnittstelle
ISymUnmanagedWriter5-Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a>Methoden  
 Diese Schnittstelle enthält die folgenden Methoden:  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[CloseMapTokensToSourceSpans-Methode](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|Schließen Sie den speziellen benutzerdefinierten Daten Abschnitt für die Übersetzung von Zuordnungsinformationen zwischen Token und Quelle. Nachdem Sie geschlossen wurde, können keine weiteren Zuordnungsinformationen mehr hinzugefügt werden.|  
|[MapTokenToSourceSpan-Methode](isymunmanagedwriter5-maptokentosourcespan-method.md)|Ordnet das angegebene Metadatentoken der angegebenen Quellzeilen Spanne in der angegebenen Quelldatei zu.<br /><br /> Muss zwischen Aufrufen der [openmaptokenstosourcespans-Methode](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) und der [closemaptokenstosourcespans-Methode](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)aufgerufen werden.|  
|[OpenMapTokensToSourceSpans-Methode](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|Öffnen Sie einen speziellen benutzerdefinierten Daten Abschnitt, um die Informationen zur Zuordnung von Token zu Quell Informationen in zu übermitteln. Wenn Sie diesen Abschnitt öffnen, wenn eine Methode bereits geöffnet ist (oder umgekehrt), ist ein Fehler aufgetreten.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen:

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter4-Schnittstelle](isymunmanagedwriter4-interface.md)
