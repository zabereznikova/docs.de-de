---
title: ISymUnmanagedReader::Initialize-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
ms.openlocfilehash: ca34d1d84d6f9960d021c35566f8412df321464d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429739"
---
# <a name="isymunmanagedreaderinitialize-method"></a>ISymUnmanagedReader::Initialize-Methode
Initialisiert den Symbol Reader mit der metadatenimporterschnittstelle, der dieser Reader zugeordnet ist, zusammen mit dem Dateinamen des Moduls.  
  
> [!NOTE]
> Diese Methode kann nur einmal aufgerufen werden und muss vor allen anderen Reader-Methoden aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a>Parameter  
 `importer`  
 in Die metadatenimporterschnittstelle, der dieser Reader zugeordnet wird.  
  
 `filename`  
 in Der Dateiname des Moduls. Sie können stattdessen den `pIStream`-Parameter verwenden.  
  
 `searchPath`  
 in Der zu durchsuchende Pfad. Dieser Parameter ist optional.  
  
 `pIStream`  
 in Der Dateistream, der als Alternative zum filename-Parameter verwendet wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="remarks"></a>Hinweise  
 Sie müssen nur einen der `filename` oder die `pIStream` Parameter angeben, nicht beides. Der Parameter `searchPath` ist optional.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
