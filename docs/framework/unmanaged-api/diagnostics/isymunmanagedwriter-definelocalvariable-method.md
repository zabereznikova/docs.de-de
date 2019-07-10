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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9466df3f6413f86eb8558f0037b96c254b2a2e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777340"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a>ISymUnmanagedWriter::DefineLocalVariable-Methode
Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich. Diese Methode kann mehrmals für eine Variable mit dem gleichen Namen aufgerufen werden, die mehrfach in einem Bereich verfügt. In diesem Fall jedoch die Werte der `startOffset` und `endOffset` Parameter dürfen sich nicht überschneiden.  
  
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
 [in] Ein Zeiger auf eine `WCHAR` , die Namen den lokalen Variablen definiert.  
  
 `attributes`  
 [in] Die Attribute der lokalen Variablen.  
  
 `cSig`  
 [in] Ein `ULONG32` , die Größe in Bytes angibt, der die `signature` Puffer.  
  
 `signature`  
 [in] Die Signatur der lokalen Variablen.  
  
 `addrKind`  
 [in] Der Adresstyp.  
  
 `addr1`  
 [in] Die erste Adresse für die Parameterangabe.  
  
 `addr2`  
 [in] Die zweite Adresse für die Parameterangabe.  
  
 `addr3`  
 [in] Die dritte Adresse für die Parameterangabe.  
  
 `startOffset`  
 [in] Der Anfangsoffset der Variablen. Dieser Parameter ist optional. Wenn dies 0 ist, wird dieser Parameter wird ignoriert, und die Variable ist im gesamten Gültigkeitsbereich definiert. Wenn es sich um einen Wert ungleich NULL ist, fällt die Variable, in die Offsets des aktuellen Gültigkeitsbereichs.  
  
 `endOffset`  
 [in] Der Endoffset der Variablen. Dieser Parameter ist optional. Wenn dies 0 ist, wird dieser Parameter wird ignoriert, und die Variable ist im gesamten Gültigkeitsbereich definiert. Wenn es sich um einen Wert ungleich NULL ist, fällt die Variable, in die Offsets des aktuellen Gültigkeitsbereichs.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [DefineGlobalVariable-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
- [DefineLocalVariable2-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
