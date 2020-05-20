---
title: ISymUnmanagedReader2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2
helpviewer_keywords:
- ISymUnmanagedReader2 interface [.NET Framework debugging]
ms.assetid: a01a881b-82a3-4b3e-a3a9-9dc305c2e5f7
topic_type:
- apiref
ms.openlocfilehash: d4c5ff46d37b1292059b18920abd8042c18bbf31
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615396"
---
# <a name="isymunmanagedreader2-interface"></a>ISymUnmanagedReader2-Schnittstelle
Stellt einen Symbol Reader dar, der den Zugriff auf Dokumente, Methoden und Variablen in einem Symbol Speicher ermöglicht. Diese Schnittstelle erweitert die [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetMethodByVersionPreRemap-Methode](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|Sie erhalten eine Symbol Lesemethode, wenn Sie über ein Methoden Token und eine Edit-and-Continue-Versionsnummer verfügen.|  
|[GetMethodsInDocument-Methode](isymunmanagedreader2-getmethodsindocument-method.md)|Ruft jede Methode ab, die im angegebenen Dokument über Zeilen Informationen verfügt.|  
|[GetSymAttributePreRemap-Methode](isymunmanagedreader2-getsymattributepreremap-method.md)|Ruft ein benutzerdefiniertes Attribut basierend auf seinem Namen ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedReader-Schnittstelle](isymunmanagedreader-interface.md)
