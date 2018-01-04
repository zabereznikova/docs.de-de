---
title: ISymUnmanagedWriter::DefineField-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineField
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51adddc6a8e58846ebefe3c130adaa670c8351e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefinefield-method"></a>ISymUnmanagedWriter::DefineField-Methode
Definiert eine einzelne Variable, die nicht innerhalb einer Methode ist. Diese Methode ist für bestimmte Felder in Klassen, Bitfelder usw. verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a>Parameter  
 `parent`  
 [in] Die Metadatentyp oder Methode token.  
  
 `name`  
 [in] Name des Felds.  
  
 `attributes`  
 [in] Die Attribute des Felds.  
  
 `cSig`  
 [in] Ein `ULONG32` d. h. die Größe in Zeichen des Puffers benötigt, damit die Signatur des Felds enthalten.  
  
 `signature`  
 [in] Das Array von Feldsignaturen.  
  
 `addrKind`  
 [in] Der Adresstyp.  
  
 `addr1`  
 [in] Die erste Adresse für die Feldangabe.  
  
 `addr2`  
 [in] Die zweite Adresse für die Feldangabe.  
  
 `addr3`  
 [in] Die dritte Adresse für die Feldangabe.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
