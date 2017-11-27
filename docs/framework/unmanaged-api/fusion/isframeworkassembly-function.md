---
title: IsFrameworkAssembly-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IsFrameworkAssembly
api_location: fusion.dll
api_type: COM
f1_keywords: IsFrameworkAssembly
helpviewer_keywords: IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 216a7221550cb6345b29b5ed9e45b13ce40eadf4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
 [in] Der Name der Assembly zu überprüfen.  
  
 `pbIsFrameworkAssembly`  
 [out] Ein boolescher Wert, der angibt, ob die Assembly verwaltet wird.  
  
 `pwzFrameworkAssemblyIdentity`  
 [in] Eine uncanonicalized Zeichenfolge, die eindeutige Identität der Assembly enthält.  
  
 `pccSize`  
 [in] Die Größe des `pwzFrameworkAssemblyIdentity`.  
  
## <a name="remarks"></a>Hinweise  
 Die `pwzAssemblyReference` Parameter ist ein Zeiger auf eine Zeichenfolge, die den Namen einer Assembly enthält.  
  
 Wenn diese Assembly Bestandteil von .NET Framework ist die `pbIsFrameworkAssembly` Parameter enthält einen booleschen Wert des `true`.  
  
 Wenn der benannte Assembly kein Bestandteil von .NET Framework ist oder wenn die `pwzAssemblyReference` Parameter wird nicht den Namen einer Assembly `pbIsFrameworkAssembly` enthält einen booleschen Wert des `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Globale statische Fusionsfunktionen](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
