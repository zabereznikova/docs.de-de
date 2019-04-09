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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 661c27b9c21f77104b8a86163d3c92d44f8a85df
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181778"
---
# <a name="isymunmanagedreaderinitialize-method"></a>ISymUnmanagedReader::Initialize-Methode
Initialisiert den Symbolreader mit der Metadaten-Importer-Tool-Schnittstelle, der dieser Reader zugeordnet wird, zusammen mit den Dateinamen des Moduls werden soll.  
  
> [!NOTE]
>  Diese Methode kann nur einmal aufgerufen werden und muss vor alle anderen Reader-Methoden aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a>Parameter  
 `importer`  
 [in] Die Metadaten-Importer-Tool-Schnittstelle mit der dieser Reader zugewiesen werden soll.  
  
 `filename`  
 [in] Der Dateiname des Moduls. Sie können die `pIStream` Parameter stattdessen.  
  
 `searchPath`  
 [in] Der Pfad zu suchen. Dieser Parameter ist optional.  
  
 `pIStream`  
 [in] Der Dateistream, der als Alternative zu den Filename-Parameter verwendet.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="remarks"></a>Hinweise  
 Sie müssen nur eine der angeben der `filename` oder die `pIStream` nicht beide Parameter. Der Parameter `searchPath` ist optional.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
