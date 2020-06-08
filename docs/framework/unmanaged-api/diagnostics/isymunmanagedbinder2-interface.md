---
title: ISymUnmanagedBinder2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2 Interface
helpviewer_keywords:
- ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type:
- apiref
ms.openlocfilehash: f6155eb777b5071ff522af4f27d5fb2d73aa25ef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501832"
---
# <a name="isymunmanagedbinder2-interface"></a>ISymUnmanagedBinder2-Schnittstelle
Stellt einen Symbol Binder für nicht verwalteten Code dar und erweitert die [ISymUnmanagedBinder](isymunmanagedbinder-interface.md) -Schnittstelle.  
  
> [!IMPORTANT]
> Es ist ein Sicherheitsrisiko, eine Programm Datenbankdatei (PDB-Datei) aus einer nicht vertrauenswürdigen Quelle zu öffnen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetReaderForFile2-Methode](isymunmanagedbinder2-getreaderforfile2-method.md)|Gibt bei Angabe einer Metadatenschnittstelle und eines Datei namens die korrekte [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle zurück, die die dem Modul zugeordneten Debugsymbole liest. Bietet eine umfassendere Suche als die [ISymUnmanagedBinder:: GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md) -Methode.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen:

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder-Schnittstelle](isymunmanagedbinder-interface.md)
- [ISymUnmanagedBinder3-Schnittstelle](isymunmanagedbinder3-interface.md)
