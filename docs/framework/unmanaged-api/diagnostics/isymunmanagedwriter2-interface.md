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
ms.openlocfilehash: 1fe6055d930c6d30e947d6bc774d0520a9e175ae
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614681"
---
# <a name="isymunmanagedwriter2-interface"></a>ISymUnmanagedWriter2-Schnittstelle
Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenz Punkten, lexikalischen Bereichen und Variablen bereit. Diese Schnittstelle erweitert die [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) -Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[DefineConstant2-Methode](isymunmanagedwriter2-defineconstant2-method.md)|Definiert einen Namen für einen konstanten Wert.|  
|[DefineGlobalVariable2-Methode](isymunmanagedwriter2-defineglobalvariable2-method.md)|Definiert eine einzelne globale Variable.|  
|[DefineLocalVariable2-Methode](isymunmanagedwriter2-definelocalvariable2-method.md)|Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
- [ISymUnmanagedWriter3-Schnittstelle](isymunmanagedwriter3-interface.md)
