---
title: ISymUnmanagedWriter::DefineParameter-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineParameter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineParameter
helpviewer_keywords:
- DefineParameter method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineParameter method [.NET Framework debugging]
ms.assetid: a8e3dd32-6a44-4371-9a74-f417b11998c8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6b01abc16334dbe091e7586efcce1c3e390a64e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedwriterdefineparameter-method"></a>ISymUnmanagedWriter::DefineParameter-Methode
Definiert einen einzelnen Parameter in der aktuellen Methode. Der Parametertyp stammt von der Position des Parameters (Sequenz) in der Signatur der Methode.  
  
 Wenn in den Metadaten für eine bestimmte Methode Parameter definiert sind, müssen Sie nicht erneut mit dieser Methode definieren. Die Symbolreader müssen die normale Metadaten für die Parameter überprüfen, bevor Sie den Symbolspeicher überprüfen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a>Parameter  
 `name`  
 [in] Der Name des Parameters.  
  
 `attributes`  
 [in] Die Parameterattribute.  
  
 `sequence`  
 [in] Die Parametersignatur.  
  
 `addrKind`  
 [in] Der Adresstyp.  
  
 `addr1`  
 [in] Die erste Adresse für die Parameterspezifikation.  
  
 `addr2`  
 [in] Die zweite Adresse für die Parameterspezifikation.  
  
 `addr3`  
 [in] Die dritte Adresse für die Parameterspezifikation.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
