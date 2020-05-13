---
title: ICorDebugSymbolProvider::GetMethodProps-Methode
ms.date: 03/30/2017
ms.assetid: 8f836b80-b7a5-460b-bf76-5f0e45652aea
ms.openlocfilehash: c9e73c4de7389405d9e4b643036709ff2dbb82e6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379567"
---
# <a name="icordebugsymbolprovidergetmethodprops-method"></a>ICorDebugSymbolProvider::GetMethodProps-Methode
Gibt Informationen zu Methodeneigenschaften wie das Metadatentoken der Methode und Informationen zu den generischen Parametern der Methode zurück, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMethodProps(  
   [in]  ULONG32 codeRva,  
   [out] mdToken *pMethodToken,  
   [out] ULONG32 *pcGenericParams,  
   [in]  ULONG32 cbSignature,  
   [out] ULONG32 *pcbSignature,  
   [out, size_is(cbSignature), length_is(*pcbSignature)] BYTE signature[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `codeRVA`  
 [in] Eine relative virtuelle Adresse in der Methode, zu der Informationen abgerufen werden.  
  
 `pMethodToken`  
 [out] Ein Zeiger auf das Metadatentoken der Methode.  
  
 `pcGenericParams`  
 [out] Ein Zeiger auf die Anzahl der generischen Parameter, die dieser Methode zugeordnet sind.  
  
 `cbSignature`  
 [in] Die Größe des `signature`-Arrays. Weitere Informationen finden Sie im Abschnitt mit den Hinweisen.  
  
 `pcbSignature`  
 [out] Ein Zeiger auf die Größe des zurückgegebenen `signature`-Arrays.  
  
 `signature`  
 [out] Ein Puffer, der die TypeSpec-Signaturen aller generischen Parameter enthält.  
  
## <a name="remarks"></a>Hinweise  
 Um die erforderliche Größe des Arrays der Methode zu erhalten `signature` , legen Sie das- `cbSignature` Argument auf 0 und `signature` auf **null**fest. Wenn die Methode zurückgegeben wird, enthält `pcbSignature` die Anzahl der für das `signature`-Array erforderlichen Bytes.  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [GetTypeProps-Methode](icordebugsymbolprovider-gettypeprops-method.md)
- [ICorDebugSymbolProvider-Schnittstelle](icordebugsymbolprovider-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
