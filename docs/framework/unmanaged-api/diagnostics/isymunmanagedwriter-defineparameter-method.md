---
title: ISymUnmanagedWriter::DefineParameter-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7fe62a8f6b48d1a9931cc0310811d7fc42f7029b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
