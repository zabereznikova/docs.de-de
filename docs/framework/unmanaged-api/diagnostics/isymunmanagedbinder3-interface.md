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
ms.openlocfilehash: 5a26de2a8f5439b7c81560927c991d449e57b76c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441590"
---
# <a name="isymunmanagedbinder3-interface"></a>ISymUnmanagedBinder3-Schnittstelle
Erweitert die Symbol Binder Schnittstelle. Rufen Sie diese Schnittstelle durch Aufrufen von `QueryInterface` für ein Objekt ab, das die- `ISymUnmanagedBinder` Schnittstelle implementiert  
  
> [!IMPORTANT]
> Es ist ein Sicherheitsrisiko, eine Programm Datenbankdatei (PDB-Datei) aus einer nicht vertrauenswürdigen Quelle zu öffnen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetReaderFromCallback-Methode](isymunmanagedbinder3-getreaderfromcallback-method.md)|Ermöglicht dem Benutzer das implementieren oder Bereitstellen von per Callback entweder `IID_IDiaReadExeAtRVACallback` oder `IID_IDiaReadExeAtOffsetCallback` , um die debugverzeichnisinformationen aus dem Arbeitsspeicher zu erhalten.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder-Schnittstelle](isymunmanagedbinder-interface.md)
- [ISymUnmanagedBinder2-Schnittstelle](isymunmanagedbinder2-interface.md)
