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
ms.openlocfilehash: deb3a28ffb73754b4c03496a6a72325418f1a4fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722907"
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
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
- [CloseMethod-Methode](isymunmanagedwriter-closemethod-method.md)
- [OpenMethod2-Methode](isymunmanagedwriter3-openmethod2-method.md)
