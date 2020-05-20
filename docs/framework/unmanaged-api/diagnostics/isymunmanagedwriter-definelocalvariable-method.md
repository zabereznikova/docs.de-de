---
title: ISymUnmanagedWriter::DefineLocalVariable-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
ms.openlocfilehash: 5730cdd910257d762230f5e54576d5e0a7ac1adb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614824"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a>ISymUnmanagedWriter::DefineLocalVariable-Methode
Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich. Diese Methode kann mehrmals für eine Variable mit demselben Namen aufgerufen werden, die über mehrere Häuser innerhalb eines Bereichs verfügt. In diesem Fall dürfen sich die Werte des `startOffset` -Parameters und des- `endOffset` Parameters jedoch nicht überlappen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a>Parameter  
 `name`  
 in Ein Zeiger auf einen `WCHAR` , der den Namen der lokalen Variablen definiert.  
  
 `attributes`  
 in Die Attribute der lokalen Variablen.  
  
 `cSig`  
 in Eine `ULONG32` , die die Größe des Puffers in Bytes angibt `signature` .  
  
 `signature`  
 in Die Signatur der lokalen Variablen.  
  
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
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
- [DefineGlobalVariable-Methode](isymunmanagedwriter-defineglobalvariable-method.md)
- [DefineLocalVariable2-Methode](isymunmanagedwriter2-definelocalvariable2-method.md)
