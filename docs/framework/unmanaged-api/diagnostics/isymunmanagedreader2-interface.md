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
ms.openlocfilehash: 3f34be833d3ccb5c636d2c5f18ccb6e216ef2c49
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709075"
---
# <a name="isymunmanagedreader2-interface"></a>ISymUnmanagedReader2-Schnittstelle

Stellt einen Symbolreader dar, der Zugriff auf Dokumente, Methoden und Variablen innerhalb eines Symbolspeichers bietet. Diese Schnittstelle erweitert die [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetMethodByVersionPreRemap-Methode](isymunmanagedreader2-getmethodbyversionpreremap-method.md)|Sie erhalten eine Symbol Lesemethode, wenn Sie über ein Methoden Token und eine Edit-and-Continue-Versionsnummer verfügen.|  
|[GetMethodsInDocument-Methode](isymunmanagedreader2-getmethodsindocument-method.md)|Ruft jede Methode ab, die im angegebenen Dokument über Zeilen Informationen verfügt.|  
|[GetSymAttributePreRemap-Methode](isymunmanagedreader2-getsymattributepreremap-method.md)|Ruft ein benutzerdefiniertes Attribut basierend auf seinem Namen ab.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedReader-Schnittstelle](isymunmanagedreader-interface.md)
