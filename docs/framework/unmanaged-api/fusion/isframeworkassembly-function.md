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
ms.openlocfilehash: 989d046bba1ba3170649e9d908a850bd1177fdd2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773834"
---
# <a name="isframeworkassembly-function"></a>IsFrameworkAssembly-Funktion
Ruft einen Wert, der angibt, ob die angegebene Assembly verwaltet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a>Parameter  
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
