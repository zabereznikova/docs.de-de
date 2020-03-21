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
ms.openlocfilehash: 40df78cdf99c2e0f53be9664f3f5c6386b6c6f93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179395"
---
# <a name="getscope2-method"></a>GetScope2-Methode
Ruft einen Importbereich ab.  
  
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
 ID der Datei, aus der importiert werden soll.  
  
 `dwScope`  
 Nullbasierter Bereich zum Importieren.  
  
 `ppImportScope`  
 Empfängt Zeiger auf [IMetaDataImport2-Schnittstelle](../metadata/imetadataimport2-interface.md) für den angegebenen Bereich.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 Erfordert alink.h.  
  
## <a name="see-also"></a>Weitere Informationen

- [IALink2-Schnittstelle](ialink2-interface.md)
- [IALink-Schnittstelle](ialink-interface.md)
- [Alink-API](index.md)
