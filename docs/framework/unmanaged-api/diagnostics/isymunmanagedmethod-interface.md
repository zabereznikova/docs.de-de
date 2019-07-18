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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c29656a4787c674886505a3be2508470460dfc10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939528"
---
# <a name="isymunmanagedmethod-interface"></a>ISymUnmanagedMethod-Schnittstelle
Stellt eine Methode in den Symbolspeicher. Diese Schnittstelle bietet Zugriff auf nur die Symbol-bezogene Attribute einer Methode, statt die Typ-bezogenen Attribute.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetNamespace-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|Ruft den Namespace, in dem diese Methode definiert ist.|  
|[GetOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|Gibt den Offset innerhalb dieser Methode entspricht, die an einer bestimmten Position in einem Dokument zurück.|  
|[GetParameters-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|Ruft die Parameter für diese Methode ab.|  
|[GetRanges-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|Gibt bei Angabe einer Position in einem Dokument ein Array von Start- / Endoffsetpaaren, die entsprechen, die den Bereichen Microsoft intermediate Language (MSIL), die die Position innerhalb dieser Methode abgedeckt werden.|  
|[GetRootScope-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|Ruft den lexikalischen Stammgültigkeitsbereich innerhalb dieser Methode ab. Dieser Gültigkeitsbereich umfasst die gesamte Methode.|  
|[GetScopeFromOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|Ruft den umfassendsten lexikalischen Gültigkeitsbereich innerhalb dieser Methode, die den angegebenen Offset einschließt.|  
|[GetSequencePointCount-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|Ruft die Anzahl der Sequenzpunkte innerhalb dieser Methode ab.|  
|[GetSequencePoints-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|Ruft die Sequenzpunkte innerhalb dieser Methode ab.|  
|[GetSourceStartEnd-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|Ruft die Dokumentpositionen für Start- und Endzeit für die Quelle dieser Methode ab.|  
|[GetToken-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|Gibt das Metadatentoken für diese Methode zurück.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
