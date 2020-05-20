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
ms.openlocfilehash: 1ee406c97fa4ccb7f87098cba2925568d8ce069f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615344"
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
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedScope2-Schnittstelle](isymunmanagedscope2-interface.md)
