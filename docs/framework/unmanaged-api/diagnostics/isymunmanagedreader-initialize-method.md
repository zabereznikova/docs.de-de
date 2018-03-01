---
title: ISymUnmanagedReader::Initialize-Methode
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 433cd62f7801d386f3b34b7fc8e95bd1d0c5f765
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreaderinitialize-method"></a>ISymUnmanagedReader::Initialize-Methode
Initialisiert den Symbolreader mit der Schnittstelle für die Metadaten, der dieser Reader zugeordnet wird, zusammen mit den Dateinamen des Moduls werden soll.  
  
> [!NOTE]
>  Diese Methode kann nur einmal aufgerufen werden und muss vor anderen Reader-Methoden aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
#### <a name="parameters"></a>Parameter  
 `importer`  
 [in] Die Metadaten-Importer-Tool-Schnittstelle mit der dieser Reader zugewiesen werden soll.  
  
 `filename`  
 [in] Der Dateiname des Moduls. Sie können die `pIStream` Parameter stattdessen.  
  
 `searchPath`  
 [in] Der Pfad zu suchen. Dieser Parameter ist optional.  
  
 `pIStream`  
 [in] Die Dateidatenstrom, der als Alternative zum Filename-Parameter verwendet wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="remarks"></a>Hinweise  
 Müssen Sie nur einen angeben der `filename` oder `pIStream` Parameter, nicht beides. Der Parameter `searchPath` ist optional.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
