---
title: IMetaDataTables::GetNextUserString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
ms.openlocfilehash: bb53d980a7b2121854748d5117bc539fed125163
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680364"
---
# <a name="imetadatatablesgetnextuserstring-method"></a>IMetaDataTables::GetNextUserString-Methode

Ruft den Index der Zeile ab, die die nächste hart codierte Zeichenfolge in der aktuellen Tabellenspalte enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `ixUserString`  
 in Ein Indexwert aus der aktuellen Zeichen folgen Spalte.  
  
 `pNext`  
 vorgenommen Ein Zeiger auf den Zeilen Index der nächsten Zeichenfolge in der Spalte.  
  
## <a name="remarks"></a>Hinweise  

 Die Verwendung dieser Methode wird nicht empfohlen, da Sie keine konsistenten Ergebnisse zurückgibt. Weitere Informationen zur GUID-Tabelle finden Sie in der Common Language Infrastructure (CLI)-Dokumentation, insbesondere "Partition II: Metadatendefinition und Semantik". Die Dokumentation ist online verfügbar. Weitere Informationen finden Sie unter [ECMA c# und Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) und [Standard-ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataTables-Schnittstelle](imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](imetadatatables2-interface.md)
