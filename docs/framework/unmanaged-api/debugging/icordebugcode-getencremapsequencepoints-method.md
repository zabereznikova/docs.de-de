---
title: ICorDebugCode::GetEnCRemapSequencePoints-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetEnCRemapSequencePoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetEnCRemapSequencePoints
helpviewer_keywords:
- GetEnCRemapSequencePoints method [.NET Framework debugging]
- ICorDebugCode::GetEnCRemapSequencePoints method [.NET Framework debugging]
ms.assetid: 8463a98a-de4a-418e-beb0-9611885ae6b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 785defaa69609fc30852be9996531e6063586ceb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750175"
---
# <a name="icordebugcodegetencremapsequencepoints-method"></a>ICorDebugCode::GetEnCRemapSequencePoints-Methode
Diese Methode ist nicht in der aktuellen Version von .NET Framework implementiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetEnCRemapSequencePoints(  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        ULONG32 offsets[]  
);  
```  
  
## <a name="see-also"></a>Siehe auch
