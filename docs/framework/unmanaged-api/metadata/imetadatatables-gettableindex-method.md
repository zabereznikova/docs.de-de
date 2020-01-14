---
title: IMetaDataTables::GetTableIndex-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type:
- apiref
ms.openlocfilehash: d3e056bc93c2faf2b1509536b8d8d4df6886dd20
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937382"
---
# <a name="imetadatatablesgettableindex-method"></a>IMetaDataTables::GetTableIndex-Methode
Ruft den Index für die Tabelle ab, auf die durch das angegebene Token verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `token`  
 in Das Token, das auf die Tabelle verweist.  
  
 `pixTbl`  
 vorgenommen Ein Zeiger auf den zurückgegebenen Index für die Tabelle, auf die verwiesen wird.  
  
## <a name="remarks"></a>Hinweise  
 Die Verwendung dieser Methode wird nicht empfohlen, da Sie keine konsistenten Ergebnisse zurückgibt. Weitere Informationen zur GUID-Tabelle finden Sie in der Common Language Infrastructure (CLI)-Dokumentation, insbesondere "Partition II: Metadatendefinition und Semantik". Die Dokumentation ist online verfügbar. Weitere Informationen finden Sie unter [ECMA C# und Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) und [Standard-ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataTables-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [IMetaDataTables2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
