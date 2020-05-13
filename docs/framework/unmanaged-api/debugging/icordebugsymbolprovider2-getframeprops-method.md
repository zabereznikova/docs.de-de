---
title: ICorDebugSymbolProvider2::GetFrameProps-Methode
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
ms.openlocfilehash: ad44c5a7b2d901967ae354f3c30218a8c7f2c2de
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379337"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a>ICorDebugSymbolProvider2::GetFrameProps-Methode
Gibt die relative virtuelle Startadresse einer Methode und den übergeordneten Frame zurück, wenn eine coderelative virtuelle Adresse angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `codeRva`  
 [in] Eine coderelative virtuelle Adresse.  
  
 `pCodeStartRva`  
 [out] Ein Zeiger auf die relative virtuelle Startadresse der Methode.  
  
 `pParentFrameStartRva`  
 [out] Ein Zeiger auf die relative virtuelle Startadresse des Frames.  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugSymbolProvider2-Schnittstelle](icordebugsymbolprovider2-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
