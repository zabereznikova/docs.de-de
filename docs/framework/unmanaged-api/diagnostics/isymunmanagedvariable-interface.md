---
title: ISymUnmanagedVariable-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 50c38c5a9e1799a460c5be1f7234b36968dc3da2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706890"
---
# <a name="isymunmanagedvariable-interface"></a>ISymUnmanagedVariable-Schnittstelle
Stellt eine Variable ein, z. B. ein Parameter, eine lokale Variable oder ein Feld dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetAddressField1-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|Ruft das erste Adressfeld für diese Variable ab. Die Bedeutung, hängt von der Art der Adresse ab.|  
|[GetAddressField2-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|Ruft das zweite Adressfeld für diese Variable ab. Die Bedeutung, hängt von der Art der Adresse ab.|  
|[GetAddressField3-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|Ruft das dritte Adressfeld für diese Variable ab. Die Bedeutung, hängt von der Art der Adresse ab.|  
|[GetAddressKind-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|Ruft die Art der Adresse dieser Variablen.|  
|[GetAttributes-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|Ruft die Attributflags für diese Variable ab.|  
|[GetEndOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|Ruft den Endoffset des dieser Variablen in seinem übergeordneten Element ab.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|Ruft den Namen dieser Variablen.|  
|[GetSignature-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|Ruft die Signatur dieser Variablen ab.|  
|[GetStartOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|Ruft den Anfangsoffset dieser Variablen in seinem übergeordneten Element ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch
- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
