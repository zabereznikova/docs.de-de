---
title: ISymUnmanagedWriter3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
ms.openlocfilehash: dfc2e39a6a39e7386bd7358d422d5c6978ec42ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683289"
---
# <a name="isymunmanagedwriter3-interface"></a>ISymUnmanagedWriter3-Schnittstelle

Stellt einen Symbolwriter dar und stellt Methoden zum Definieren von Dokumenten, Sequenzpunkten, lexikalischen Bereichen und Variablen bereit. Diese Schnittstelle erweitert die [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) -Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Commit-Methode](isymunmanagedwriter3-commit-method.md)|Führt einen Commit für die bisher geschriebenen Änderungen in den Stream aus.|  
|[OpenMethod2-Methode](isymunmanagedwriter3-openmethod2-method.md)|Öffnet eine-Methode und stellt den tatsächlichen Abschnitts Offset im Bild bereit.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
- [ISymUnmanagedWriter2-Schnittstelle](isymunmanagedwriter2-interface.md)
