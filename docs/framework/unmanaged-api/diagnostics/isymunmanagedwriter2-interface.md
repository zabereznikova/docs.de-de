---
title: ISymUnmanagedWriter2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
ms.openlocfilehash: 6feb48b7c78dda64ba372e470b83ffb14f21f2f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683328"
---
# <a name="isymunmanagedwriter2-interface"></a>ISymUnmanagedWriter2-Schnittstelle

Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenzpunkten, lexikalischen Bereichen und Variablen bereit. Diese Schnittstelle erweitert die [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) -Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[DefineConstant2-Methode](isymunmanagedwriter2-defineconstant2-method.md)|Definiert einen Namen für einen konstanten Wert.|  
|[DefineGlobalVariable2-Methode](isymunmanagedwriter2-defineglobalvariable2-method.md)|Definiert eine einzelne globale Variable.|  
|[DefineLocalVariable2-Methode](isymunmanagedwriter2-definelocalvariable2-method.md)|Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
- [ISymUnmanagedWriter3-Schnittstelle](isymunmanagedwriter3-interface.md)
