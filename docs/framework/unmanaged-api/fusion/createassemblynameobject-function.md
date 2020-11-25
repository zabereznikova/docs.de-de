---
title: CreateAssemblyNameObject-Funktion
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
ms.openlocfilehash: 995f1064c2f40005c4a19ef034d7edfd668b5d51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704161"
---
# <a name="createassemblynameobject-function"></a>CreateAssemblyNameObject-Funktion

Ruft einen Schnittstellen Zeiger auf eine [IAssemblyName](iassemblyname-interface.md) -Instanz ab, die die eindeutige Identität der Assembly mit dem angegebenen Namen darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a>Parameter  

 `ppAssemblyNameObj`  
 vorgenommen Der zurückgegebene `IAssemblyName` .  
  
 `szAssemblyName`  
 in Der Name der Assembly, für die die neue Instanz erstellt werden soll `IAssemblyName` .  
  
 `dwFlags`  
 in Flags, die an den Objektkonstruktor übergeben werden sollen.  
  
 `pvReserved`  
 [in] Für zukünftige Erweiterungen reserviert. `pvReserved` muss ein NULL-Verweis sein.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Fusion. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IAssemblyName-Schnittstelle](iassemblyname-interface.md)
- [Fusion – Globale statistische Funktionen](fusion-global-static-functions.md)
