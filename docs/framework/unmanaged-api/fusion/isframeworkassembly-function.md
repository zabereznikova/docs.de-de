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
ms.openlocfilehash: 828c7660d6c006e700302d119ce4caf7d76e5d84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728562"
---
# <a name="isframeworkassembly-function"></a>IsFrameworkAssembly-Funktion

Ruft einen Wert ab, der angibt, ob die angegebene Assembly verwaltet wird.  
  
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
 in Der Name der zu Überprüfung enden Assembly.  
  
 `pbIsFrameworkAssembly`  
 vorgenommen Ein boolescher Wert, der angibt, ob die Assembly verwaltet wird.  
  
 `pwzFrameworkAssemblyIdentity`  
 in Eine nicht kanonische Zeichenfolge, die die eindeutige Identität der Assembly enthält.  
  
 `pccSize`  
 [in] Die Größe des `pwzFrameworkAssemblyIdentity`.  
  
## <a name="remarks"></a>Hinweise  

 Der- `pwzAssemblyReference` Parameter ist ein Zeiger auf eine Zeichenfolge, die den Namen einer Assembly enthält.  
  
 Wenn diese Assembly Teil des .NET Framework ist, enthält der- `pbIsFrameworkAssembly` Parameter den booleschen Wert `true` .  
  
 Wenn die benannte Assembly nicht Teil der .NET Framework ist, oder wenn der- `pwzAssemblyReference` Parameter keine Assembly benannt hat, `pbIsFrameworkAssembly` enthält einen booleschen Wert von `false` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Fusion – Globale statistische Funktionen](fusion-global-static-functions.md)
