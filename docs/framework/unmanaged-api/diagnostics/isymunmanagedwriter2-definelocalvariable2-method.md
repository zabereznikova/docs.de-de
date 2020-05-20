---
title: ISymUnmanagedWriter2::DefineLocalVariable2-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
ms.openlocfilehash: ac7559bd5431f45b266602404ddde9081aa2944d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614694"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a>ISymUnmanagedWriter2::DefineLocalVariable2-Methode
Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich. Diese Methode kann mehrmals für eine Variable mit demselben Namen aufgerufen werden, die über mehrere Häuser innerhalb eines Bereichs verfügt. In diesem Fall dürfen sich die Werte des `startOffset` -Parameters und des- `endOffset` Parameters jedoch nicht überlappen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a>Parameter  
 `name`  
 in Der Name der lokalen Variablen.  
  
 `attributes`  
 in Die Attribute der lokalen Variablen.  
  
 `sigToken`  
 in Das Metadatentoken der Signatur.  
  
 `addrKind`  
 in Der adrestyp.  
  
 `addr1`  
 in Die erste Adresse für die Parameter Spezifikation.  
  
 `addr2`  
 in Die zweite Adresse für die Parameter Spezifikation.  
  
 `addr3`  
 in Die dritte Adresse für die Parameter Spezifikation.  
  
 `startOffset`  
 in Der Anfangs Offset für die Variable. Dieser Parameter ist optional. Wenn der Wert 0 ist, wird dieser Parameter ignoriert, und die Variable wird im gesamten Bereich definiert. Wenn es sich um einen Wert ungleich 0 (null) handelt, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeits Bereichs.  
  
 `endOffset`  
 in Der Endoffset für die Variable. Dieser Parameter ist optional. Wenn der Wert 0 ist, wird dieser Parameter ignoriert, und die Variable wird im gesamten Bereich definiert. Wenn es sich um einen Wert ungleich 0 (null) handelt, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeits Bereichs.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Corsym. idl  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter2-Schnittstelle](isymunmanagedwriter2-interface.md)
- [DefineLocalVariable-Methode](isymunmanagedwriter-definelocalvariable-method.md)
