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
ms.openlocfilehash: 93e1f8eb17f06e42ddb243f88c593979fcb28030
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733281"
---
# <a name="isymunmanagedvariable-interface"></a>ISymUnmanagedVariable-Schnittstelle

Stellt eine Variable dar (z. B. einen Parameter, eine lokale Variable oder ein Feld).  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetAddressField1-Methode](isymunmanagedvariable-getaddressfield1-method.md)|Ruft das erste Adressfeld für diese Variable ab. Ihre Bedeutung hängt von der Art der Adresse ab.|  
|[GetAddressField2-Methode](isymunmanagedvariable-getaddressfield2-method.md)|Ruft das zweite Adressfeld für diese Variable ab. Ihre Bedeutung hängt von der Art der Adresse ab.|  
|[GetAddressField3-Methode](isymunmanagedvariable-getaddressfield3-method.md)|Ruft das dritte Adressfeld für diese Variable ab. Ihre Bedeutung hängt von der Art der Adresse ab.|  
|[GetAddressKind-Methode](isymunmanagedvariable-getaddresskind-method.md)|Ruft die Art der Adresse dieser Variablen ab.|  
|[GetAttributes-Methode](isymunmanagedvariable-getattributes-method.md)|Ruft die Attributflags für diese Variable ab.|  
|[GetEndOffset-Methode](isymunmanagedvariable-getendoffset-method.md)|Ruft den Endoffset dieser Variablen in ihrem übergeordneten Element ab.|  
|[GetName-Methode](isymunmanagedvariable-getname-method.md)|Ruft den Namen dieser Variablen ab.|  
|[GetSignature-Methode](isymunmanagedvariable-getsignature-method.md)|Ruft die Signatur dieser Variablen ab.|  
|[GetStartOffset-Methode](isymunmanagedvariable-getstartoffset-method.md)|Ruft den Start Offset dieser Variablen in ihrem übergeordneten Element ab.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
