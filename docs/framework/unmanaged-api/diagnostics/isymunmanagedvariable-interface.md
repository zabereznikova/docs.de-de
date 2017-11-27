---
title: ISymUnmanagedVariable-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable
helpviewer_keywords: ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c32d5b66c575a21b4d390cff560b71f93aa31927
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariable-interface"></a>ISymUnmanagedVariable-Schnittstelle
Stellt eine Variable, z. B. einen Parameter, eine lokale Variable oder ein Feld dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetAddressField1-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|Ruft das Feld für die erste Adresse für diese Variable ab. Seiner Bedeutung hängt von der Art der Adresse ab.|  
|[GetAddressField2-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|Ruft das zweite Adressfeld für diese Variable ab. Seiner Bedeutung hängt von der Art der Adresse ab.|  
|[GetAddressField3-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|Ruft das Feld für die dritte Adresse für diese Variable ab. Seiner Bedeutung hängt von der Art der Adresse ab.|  
|[GetAddressKind-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|Ruft die Art der Adresse dieser Variablen ab.|  
|[GetAttributes-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|Ruft die Attributflags für diese Variable ab.|  
|[GetEndOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|Ruft den Endoffset dieser Variablen in seinem übergeordneten Element ab.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|Ruft den Namen der Variablen ab.|  
|[GetSignature-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|Ruft die Signatur dieser Variablen ab.|  
|[GetStartOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|Ruft den Anfangsoffset der Variablen in seinem übergeordneten Element ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
