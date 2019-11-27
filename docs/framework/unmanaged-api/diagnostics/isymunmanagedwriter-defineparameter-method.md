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
ms.openlocfilehash: bc1b65de026a674a3dff183050a5a205fd7052c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427997"
---
# <a name="isymunmanagedwriterdefineparameter-method"></a>ISymUnmanagedWriter::DefineParameter-Methode
Definiert einen einzelnen Parameter in der aktuellen Methode. Der Parametertyp wird aus der Position (Sequence) des Parameters innerhalb der Signatur der Methode entnommen.  
  
 Wenn Parameter in den Metadaten für eine bestimmte Methode definiert sind, müssen Sie Sie nicht mit dieser Methode erneut definieren. Die Symbol Leser müssen die normalen Metadaten für die Parameter überprüfen, bevor Sie den Symbol Speicher überprüfen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT DefineParameter(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      sequence,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a>Parameter  
 `name`  
 in Der Parameter Name.  
  
 `attributes`  
 in Die Parameter Attribute.  
  
 `sequence`  
 in Die Parameter Signatur.  
  
 `addrKind`  
 in Der adrestyp.  
  
 `addr1`  
 in Die erste Adresse für die Parameter Spezifikation.  
  
 `addr2`  
 in Die zweite Adresse für die Parameter Spezifikation.  
  
 `addr3`  
 in Die dritte Adresse für die Parameter Spezifikation.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
