---
title: ISymUnmanagedWriter::GetDebugInfo-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.GetDebugInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type:
- apiref
ms.openlocfilehash: dcab63b603d4a9a8e1430228043d2a5e597bbf4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678291"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>ISymUnmanagedWriter::GetDebugInfo-Methode

Gibt die erforderlichen Informationen zurück, damit ein Compiler den Debugverzeichniseintrag im PE-Dateiheader schreiben muss. Der Symbolwriter füllt alle Felder mit Ausnahme von `TimeDateStamp` und aus `PointerToRawData` . (Der Compiler ist dafür verantwortlich, diese beiden Felder entsprechend festzulegen.)  
  
 Ein Compiler sollte diese Methode abrufen, das Daten-BLOB an die PE-Datei ausgeben, das Feld in der IMAGE_DEBUG_DIRECTORY so festlegen, dass es `PointerToRawData` auf die ausgegebenen Daten verweist, und die IMAGE_DEBUG_DIRECTORY in die PE-Datei schreiben. Der Compiler sollte außerdem festlegen `TimeDateStamp` , dass das-Feld gleich dem `TimeDateStamp` der generierten PE-Datei ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a>Parameter  

 `pIDD`  
 [in, out] Ein Zeiger auf einen IMAGE_DEBUG_DIRECTORY, den der Symbolwriter ausfüllen wird.  
  
 `cData`  
 in Ein-Wert `DWORD` , der die Größe der Debugdaten enthält.  
  
 `pcData`  
 vorgenommen Ein Zeiger auf einen `DWORD` , der die Größe des Puffers empfängt, der zum enthalten der Debugdaten erforderlich ist.  
  
 `data`  
 vorgenommen Ein Zeiger auf einen Puffer, der groß genug ist, um die Debugdaten für den Symbol Speicher zu speichern.  
  
## <a name="return-value"></a>Rückgabewert  

 S_OK, wenn die Methode erfolgreich ist. andernfalls E_FAIL oder ein anderer Fehlercode.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Header:** Corsym. idl, corsym. h  
  
## <a name="see-also"></a>Weitere Informationen

- [ISymUnmanagedWriter-Schnittstelle](isymunmanagedwriter-interface.md)
