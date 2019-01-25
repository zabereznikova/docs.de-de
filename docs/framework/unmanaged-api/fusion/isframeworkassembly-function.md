---
title: IsFrameworkAssembly-Funktion
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e231c4fa51e6e66cba6227233cf73dd1cd4ebbe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733921"
---
# <a name="isframeworkassembly-function"></a>IsFrameworkAssembly-Funktion
Ruft einen Wert, der angibt, ob die angegebene Assembly verwaltet wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwzAssemblyReference`  
 [in] Der Name des zu überprüfenden Assembly.  
  
 `pbIsFrameworkAssembly`  
 [out] Ein boolescher Wert, der angibt, ob die Assembly verwaltet wird.  
  
 `pwzFrameworkAssemblyIdentity`  
 [in] Eine uncanonicalized-Zeichenfolge, die eindeutige Identität der Assembly enthält.  
  
 `pccSize`  
 [in] Die Größe des `pwzFrameworkAssemblyIdentity`.  
  
## <a name="remarks"></a>Hinweise  
 Die `pwzAssemblyReference` Parameter ist ein Zeiger auf eine Zeichenfolge, die den Namen einer Assembly enthält.  
  
 Wenn diese Assembly Bestandteil von .NET Framework ist die `pbIsFrameworkAssembly` Parameter enthält einen booleschen Wert der `true`.  
  
 Wenn die benannte Assembly nicht als Teil von .NET Framework ist oder wenn die `pwzAssemblyReference` Parameter gibt nicht an eine Assembly `pbIsFrameworkAssembly` enthält einen booleschen Wert der `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
## <a name="see-also"></a>Siehe auch
- [Fusion: Globale statistische Funktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
