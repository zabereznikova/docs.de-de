---
title: ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedReaderSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: fde7e21d-1169-4bed-a34d-792e69652bf9
topic_type:
- apiref
ms.openlocfilehash: e97dc1d06eb4f5eb110923db20896d7d12c41710
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446382"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a>ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle
Stellt Methoden bereit, die Symbol Suchinformationen erhalten. Rufen Sie diese Schnittstelle durch Aufrufen von `QueryInterface` für ein Objekt ab, das die [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) -Schnittstelle implementiert.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetSymbolSearchInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|Ruft Symbol Suchinformationen ab.|  
|[GetSymbolSearchInfoCount-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|Ruft die Anzahl der Symbol Suchinformationen ab.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
