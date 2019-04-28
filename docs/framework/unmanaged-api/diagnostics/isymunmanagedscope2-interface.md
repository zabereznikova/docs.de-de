---
title: ISymUnmanagedScope2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0109b25b1cdc42204fc4873577e495641c4ec4fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761571"
---
# <a name="isymunmanagedscope2-interface"></a>ISymUnmanagedScope2-Schnittstelle
Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar. Diese Schnittstelle erweitert die [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) Schnittstelle mit Methoden, die Informationen zu definierten Konstanten innerhalb des Bereichs zu erhalten.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetConstantCount-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|Ruft die Anzahl der in diesem Bereich definierten Konstanten ab.|  
|[GetConstants-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|Ruft ab, die lokalen Konstanten, die innerhalb dieses Bereichs definiert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedScope-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
