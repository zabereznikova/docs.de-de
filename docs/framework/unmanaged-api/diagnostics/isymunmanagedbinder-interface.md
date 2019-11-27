---
title: ISymUnmanagedBinder-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder
helpviewer_keywords:
- ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type:
- apiref
ms.openlocfilehash: f23df98abc5355f0b25d7253b5f2ae808b3446a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449370"
---
# <a name="isymunmanagedbinder-interface"></a>ISymUnmanagedBinder-Schnittstelle
Stellt einen Symbol Binder für nicht verwalteten Code dar.  
  
> [!IMPORTANT]
> Es ist ein Sicherheitsrisiko, eine Programm Datenbankdatei (PDB-Datei) aus einer nicht vertrauenswürdigen Quelle zu öffnen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetReaderForFile-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|Gibt bei Angabe einer Metadatenschnittstelle und eines Datei namens die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Struktur zurück, die die dem Modul zugeordneten Debugsymbole liest.|  
|[GetReaderFromStream-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|Gibt bei einer Metadatenschnittstelle und einem Stream, der den Symbol Speicher enthält, die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Struktur zurück, die die Debugsymbole aus dem angegebenen Symbol Speicher liest.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [ISymUnmanagedBinder3-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
