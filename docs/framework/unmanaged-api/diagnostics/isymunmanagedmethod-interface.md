---
title: ISymUnmanagedMethod-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
ms.openlocfilehash: 1d3ccb2265f056d5776199d997dc067c8d5513e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448788"
---
# <a name="isymunmanagedmethod-interface"></a>ISymUnmanagedMethod-Schnittstelle
Stellt eine Methode im Symbol Speicher dar. Diese Schnittstelle bietet Zugriff auf die Symbol bezogenen Attribute einer Methode anstelle der typbezogenen Attribute.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetNamespace-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|Ruft den Namespace ab, in dem diese Methode definiert ist.|  
|[GetOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|Gibt den Offset innerhalb dieser Methode zurück, der einer bestimmten Position in einem Dokument entspricht.|  
|[GetParameters-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|Ruft die Parameter für diese Methode ab.|  
|[GetRanges-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|Gibt ein Array von Start-und Endoffset Paaren zurück, die den Bereichen der Microsoft Intermediate Language (MSIL) entsprechen, die von der Position innerhalb dieser Methode abgedeckt werden, wenn eine Position in einem Dokument verfügbar ist.|  
|[GetRootScope-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|Ruft den lexikalischen Stamm Gültigkeitsbereich innerhalb dieser Methode ab. Dieser Gültigkeitsbereich umfasst die gesamte Methode.|  
|[GetScopeFromOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|Ruft den am weitesten schließenden lexikalischen Gültigkeitsbereich innerhalb dieser Methode ab, der den angegebenen Offset einschließt.|  
|[GetSequencePointCount-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|Ruft die Anzahl von Sequenz Punkten innerhalb dieser Methode ab.|  
|[GetSequencePoints-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|Ruft alle Sequenz Punkte innerhalb dieser Methode ab.|  
|[GetSourceStartEnd-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|Ruft die Start-und Enddokument Positionen für die Quelle dieser Methode ab.|  
|[GetToken-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|Gibt das Metadatentoken für diese Methode zurück.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
