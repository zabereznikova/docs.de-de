---
title: ISymUnmanagedWriter::GetDebugInfo-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.GetDebugInfo
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f071bfe88397d6431fb50403c3969d82c5cfe8fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a>ISymUnmanagedWriter::GetDebugInfo-Methode
Gibt die Informationen für einen Compiler den Debug-Verzeichniseintrag im portierbare ausführbare Datei (PE) Dateiheader schreiben erforderlich. Der Symbolwriter füllt alle Felder mit Ausnahme von `TimeDateStamp` und `PointerToRawData`. (Der Compiler ist verantwortlich für die folgenden beiden Felder entsprechend festlegen.)  
  
 Ein Compiler sollte rufen Sie diese Methode, das Daten-Blob in der PE-Datei ausgeben, Festlegen von der `PointerToRawData` Feld IMAGE_DEBUG_DIRECTORY zeigen Sie auf die ausgegebenen Daten und das IMAGE_DEBUG_DIRECTORY in die PE-Datei schreiben. Der Compiler sollte ebenfalls festgelegt. die `TimeDateStamp` Feld so, dass die `TimeDateStamp` der PE-Datei generiert wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pIDD`  
 [in, out] Ein Zeiger auf ein IMAGE_DEBUG_DIRECTORY, die der Symbolwriter ausgefüllt wird.  
  
 `cData`  
 [in] Ein `DWORD` , die die Größe der Debugdaten enthält.  
  
 `pcData`  
 [out] Ein Zeiger auf eine `DWORD` , die die Größe des Puffers erforderlich, um die Debugdaten empfängt.  
  
 `data`  
 [out] Ein Zeiger auf einen Puffer, der groß genug für die Debugdaten für den Symbolspeicher gespeichert ist.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
