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
ms.openlocfilehash: 7a98a0c40f68cef9bab1ea2de0850208aaef77a0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615123"
---
# <a name="isymunmanagedmethod-interface"></a>ISymUnmanagedMethod-Schnittstelle
Stellt eine Methode im Symbol Speicher dar. Diese Schnittstelle bietet Zugriff auf die Symbol bezogenen Attribute einer Methode anstelle der typbezogenen Attribute.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetNamespace-Methode](isymunmanagedmethod-getnamespace-method.md)|Ruft den Namespace ab, in dem diese Methode definiert ist.|  
|[GetOffset-Methode](isymunmanagedmethod-getoffset-method.md)|Gibt den Offset innerhalb dieser Methode zurück, der einer bestimmten Position in einem Dokument entspricht.|  
|[GetParameters-Methode](isymunmanagedmethod-getparameters-method.md)|Ruft die Parameter für diese Methode ab.|  
|[GetRanges-Methode](isymunmanagedmethod-getranges-method.md)|Gibt ein Array von Start-und Endoffset Paaren zurück, die den Bereichen der Microsoft Intermediate Language (MSIL) entsprechen, die von der Position innerhalb dieser Methode abgedeckt werden, wenn eine Position in einem Dokument verfügbar ist.|  
|[GetRootScope-Methode](isymunmanagedmethod-getrootscope-method.md)|Ruft den lexikalischen Stamm Gültigkeitsbereich innerhalb dieser Methode ab. Dieser Gültigkeitsbereich umfasst die gesamte Methode.|  
|[GetScopeFromOffset-Methode](isymunmanagedmethod-getscopefromoffset-method.md)|Ruft den am weitesten schließenden lexikalischen Gültigkeitsbereich innerhalb dieser Methode ab, der den angegebenen Offset einschließt.|  
|[GetSequencePointCount-Methode](isymunmanagedmethod-getsequencepointcount-method.md)|Ruft die Anzahl von Sequenz Punkten innerhalb dieser Methode ab.|  
|[GetSequencePoints-Methode](isymunmanagedmethod-getsequencepoints-method.md)|Ruft alle Sequenz Punkte innerhalb dieser Methode ab.|  
|[GetSourceStartEnd-Methode](isymunmanagedmethod-getsourcestartend-method.md)|Ruft die Start-und Enddokument Positionen für die Quelle dieser Methode ab.|  
|[GetToken-Methode](isymunmanagedmethod-gettoken-method.md)|Gibt das Metadatentoken für diese Methode zurück.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
