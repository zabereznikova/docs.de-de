---
title: GetScope2-Methode
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
ms.openlocfilehash: e8c6fd7dca13afe7504e447caca9a217c8136c27
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684524"
---
# <a name="getscope2-method"></a>GetScope2-Methode

Ruft einen Import Bereich ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;
```  
  
## <a name="parameters"></a>Parameter  

 `AssemblyID`  
 ID der Zielassembly.  
  
 `FileToken`  
 Die ID der Datei, aus der importiert werden soll.  
  
 `dwScope`  
 NULL basierter Gültigkeitsbereich, der importiert werden soll.  
  
 `ppImportScope`  
 Empfängt einen Zeiger auf eine [IMetaDataImport2-Schnittstellen](../metadata/imetadataimport2-interface.md) Schnittstelle für den angegeben Bereich.  
  
## <a name="return-value"></a>Rückgabewert  

 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 Erfordert Alink. h.  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [ALink-API](index.md)
