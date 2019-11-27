---
title: ISymUnmanagedWriter::OpenMethod-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
ms.openlocfilehash: 7b13ca9884516e95e0bb922efc5bc1a845344e38
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427921"
---
# <a name="isymunmanagedwriteropenmethod-method"></a>ISymUnmanagedWriter::OpenMethod-Methode
Öffnet eine Methode, in die Symbol Informationen ausgegeben werden. Die angegebene Methode wird zur aktuellen Methode für Aufrufe zum Definieren von Sequenz Punkten, Parametern und lexikalischen Gültigkeitsbereichen. Es gibt einen impliziten lexikalischen Gültigkeitsbereich um die gesamte Methode. Durch das erneute Öffnen einer Methode, die zuvor geschlossen war, werden alle zuvor definierten Symbole für diese Methode gelöscht. Es kann immer nur eine offene Methode vorhanden sein.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a>Parameter  
 `method`  
 in Das Metadatentoken für die Methode, die geöffnet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Siehe auch

- [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [CloseMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)
- [OpenMethod2-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-openmethod2-method.md)
