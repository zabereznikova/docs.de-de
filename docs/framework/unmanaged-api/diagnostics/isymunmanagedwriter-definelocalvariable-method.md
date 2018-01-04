---
title: ISymUnmanagedWriter::DefineLocalVariable-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineLocalVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89ea3e23166b4745b34b7c2af498d29564cdd68d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a>ISymUnmanagedWriter::DefineLocalVariable-Methode
Definiert eine einzelne Variable im aktuellen lexikalischen Gültigkeitsbereich. Diese Methode kann mehrmals für eine Variable mit dem gleichen Namen aufgerufen werden, die mehrfach in einem Bereich aufweist. In diesem Fall jedoch die Werte der `startOffset` und `endOffset` Parameter dürfen sich nicht überschneiden.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
#### <a name="parameters"></a>Parameter  
 `name`  
 [in] Ein Zeiger auf eine `WCHAR` , der Name die lokale Variable definiert.  
  
 `attributes`  
 [in] Die Attribute der lokalen Variablen.  
  
 `cSig`  
 [in] Ein `ULONG32` gibt, die die Größe in Bytes, der die `signature` Puffer.  
  
 `signature`  
 [in] Die Signatur der lokalen Variablen.  
  
 `addrKind`  
 [in] Der Adresstyp.  
  
 `addr1`  
 [in] Die erste Adresse für die Parameterspezifikation.  
  
 `addr2`  
 [in] Die zweite Adresse für die Parameterspezifikation.  
  
 `addr3`  
 [in] Die dritte Adresse für die Parameterspezifikation.  
  
 `startOffset`  
 [in] Der Anfangsoffset für die Variable. Dieser Parameter ist optional. Ist er 0, wird dieser Parameter wird ignoriert, und die Variable den gesamten Gültigkeitsbereich definiert ist. Wenn sie einen Wert ungleich NULL ist, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeitsbereichs.  
  
 `endOffset`  
 [in] Der Endoffset für die Variable. Dieser Parameter ist optional. Ist er 0, wird dieser Parameter wird ignoriert, und die Variable den gesamten Gültigkeitsbereich definiert ist. Wenn sie einen Wert ungleich NULL ist, fällt die Variable innerhalb der Offsets des aktuellen Gültigkeitsbereichs.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [DefineGlobalVariable-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)  
 [DefineLocalVariable2-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
