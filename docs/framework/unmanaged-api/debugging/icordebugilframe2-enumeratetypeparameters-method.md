---
title: ICorDebugILFrame2::EnumerateTypeParameters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7454b551edc546fecbd9d091f7c821e0a07b16df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988545"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a>ICorDebugILFrame2::EnumerateTypeParameters-Methode
Ruft ein ICorDebugTypeEnum-Objekt, enthält die <xref:System.Type> Parameter in diesem Frame.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppTyParEnum`  
 Ein Zeiger auf die Adresse des ICorDebugTypeEnum-Schnittstellenobjekts, die Enumeration von Typparametern ermöglicht.  
  
 Die Liste der Parameter vom Typ enthalten die Klassentypparameter (sofern vorhanden) gefolgt von den Methodentypparametern (sofern vorhanden).  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der [IMetaDataImport2:: EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) Methode, um zu bestimmen, wie viele Parameter vom Typ Klasse und Methode Parameter geben Sie diese Liste enthält.  
  
 Die Typparameter sind nicht immer verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
