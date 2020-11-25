---
title: ISymUnmanagedScope-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: 9256342ad3a91e6770d6fd19d9d2f94fab267d3e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725884"
---
# <a name="isymunmanagedscope-interface"></a>ISymUnmanagedScope-Schnittstelle

Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetChildren-Methode](isymunmanagedscope-getchildren-method.md)|Ruft die untergeordneten Elemente dieses Gültigkeits Bereichs ab.|  
|[GetEndOffset-Methode](isymunmanagedscope-getendoffset-method.md)|Ruft den Endoffset für diesen Bereich ab.|  
|[GetLocalCount-Methode](isymunmanagedscope-getlocalcount-method.md)|Ruft die Anzahl der in diesem Bereich definierten lokalen Variablen ab.|  
|[GetLocals-Methode](isymunmanagedscope-getlocals-method.md)|Ruft die in diesem Bereich definierten lokalen Variablen ab.|  
|[GetMethod-Methode](isymunmanagedscope-getmethod-method.md)|Ruft die Methode ab, die diesen Bereich enthält.|  
|[GetNamespaces-Methode](isymunmanagedscope-getnamespaces-method.md)|Ruft die Namespaces ab, die in diesem Bereich verwendet werden.|  
|[GetParent-Methode](isymunmanagedscope-getparent-method.md)|Ruft den übergeordneten Gültigkeitsbereich dieses Bereichs ab.|  
|[GetStartOffset-Methode](isymunmanagedscope-getstartoffset-method.md)|Ruft den Start Offset für diesen Bereich ab.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedScope2-Schnittstelle](isymunmanagedscope2-interface.md)
