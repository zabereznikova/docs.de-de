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
ms.openlocfilehash: d05d4451e8fb75829b22e0a1b9c9afcb0607eb8b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610170"
---
# <a name="isymunmanagedvariable-interface"></a>ISymUnmanagedVariable-Schnittstelle
Stellt eine Variable dar, z. b. einen Parameter, eine lokale Variable oder ein Feld.  
  
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
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [Diagnosesymbolspeicher-Schnittstellen](diagnostics-symbol-store-interfaces.md)
