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
ms.openlocfilehash: ee57ba14f048032e2cd9d0129089743c0f0304bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445974"
---
# <a name="isymunmanagedvariable-interface"></a>ISymUnmanagedVariable-Schnittstelle
Stellt eine Variable dar, z. b. einen Parameter, eine lokale Variable oder ein Feld.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetAddressField1-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|Ruft das erste Adressfeld für diese Variable ab. Ihre Bedeutung hängt von der Art der Adresse ab.|  
|[GetAddressField2-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|Ruft das zweite Adressfeld für diese Variable ab. Ihre Bedeutung hängt von der Art der Adresse ab.|  
|[GetAddressField3-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|Ruft das dritte Adressfeld für diese Variable ab. Ihre Bedeutung hängt von der Art der Adresse ab.|  
|[GetAddressKind-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|Ruft die Art der Adresse dieser Variablen ab.|  
|[GetAttributes-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|Ruft die Attributflags für diese Variable ab.|  
|[GetEndOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|Ruft den Endoffset dieser Variablen in ihrem übergeordneten Element ab.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|Ruft den Namen dieser Variablen ab.|  
|[GetSignature-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|Ruft die Signatur dieser Variablen ab.|  
|[GetStartOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|Ruft den Start Offset dieser Variablen in ihrem übergeordneten Element ab.|  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
