---
title: ISymUnmanagedBinder3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
ms.openlocfilehash: e4a415b21e3980e7603319d7acbb3831462fac9e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449296"
---
# <a name="isymunmanagedbinder3-interface"></a>ISymUnmanagedBinder3-Schnittstelle
Erweitert die Symbol Binder Schnittstelle. Rufen Sie diese Schnittstelle durch Aufrufen von `QueryInterface` für ein Objekt ab, das die `ISymUnmanagedBinder`-Schnittstelle implementiert.  
  
> [!IMPORTANT]
> Es ist ein Sicherheitsrisiko, eine Programm Datenbankdatei (PDB-Datei) aus einer nicht vertrauenswürdigen Quelle zu öffnen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetReaderFromCallback-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|Ermöglicht es dem Benutzer, entweder eine `IID_IDiaReadExeAtRVACallback` oder eine `IID_IDiaReadExeAtOffsetCallback` zu implementieren oder bereitzustellen, um die debugverzeichnisinformationen aus dem Arbeitsspeicher abzurufen.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [ISymUnmanagedBinder2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
