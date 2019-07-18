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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdfd8e8fc419809a3a490639ada1c533f286fe8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939996"
---
# <a name="isymunmanagedbinder3-interface"></a>ISymUnmanagedBinder3-Schnittstelle
Erweitert die Symbol-Binder-Schnittstelle. Rufen Sie diese Schnittstelle durch den Aufruf `QueryInterface` auf ein Objekt, implementiert die `ISymUnmanagedBinder` Schnittstelle.  
  
> [!IMPORTANT]
>  Es ist ein Sicherheitsrisiko dar, um eine Programmdatenbankdatei (PDB) aus einer nicht vertrauenswürdigen Quelle zu öffnen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetReaderFromCallback-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|Ermöglicht dem Benutzer zu implementieren, oder geben Sie entweder über den Rückruf ein `IID_IDiaReadExeAtRVACallback` oder `IID_IDiaReadExeAtOffsetCallback` die Debuginformationen für das Verzeichnis aus dem Arbeitsspeicher abrufen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [ISymUnmanagedBinder2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
