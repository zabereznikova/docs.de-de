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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fa385805d3e2dca8fef3e1490b2c67dd0583373
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755066"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a>ISymUnmanagedWriter2::DefineLocalVariable2-Methode
Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich. Diese Methode kann mehrmals für eine Variable mit dem gleichen Namen aufgerufen werden, die mehrfach in einem Bereich verfügt. In diesem Fall jedoch die Werte der `startOffset` und `endOffset` Parameter dürfen sich nicht überschneiden.  
  
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
 [in] Der Name der lokalen Variablen.  
  
 `attributes`  
 [in] Die Attribute der lokalen Variablen.  
  
 `sigToken`  
 [in] Das Metadatentoken der Signatur.  
  
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
 **Header:** CorSym.idl  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [DefineLocalVariable-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
