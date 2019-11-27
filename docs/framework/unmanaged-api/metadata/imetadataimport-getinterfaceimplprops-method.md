---
title: IMetaDataImport::GetInterfaceImplProps-Methode
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
ms.openlocfilehash: e5eb735acac73d694a0719c206bd22711a8c0333
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437536"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>IMetaDataImport::GetInterfaceImplProps-Methode
Ruft einen Zeiger auf die Metadatentoken für den <xref:System.Type> ab, der die angegebene Methode implementiert, und für die-Schnittstelle, die diese Methode deklariert.
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `iiImpl`  
 in Das Metadatentoken, das die Methode darstellt, für die die Klassen-und Schnittstellen Token zurückgegeben werden.  
  
 `pClass`  
 vorgenommen Das Metadatentoken, das die Klasse darstellt, die die Methode implementiert.  
  
 `ptkIface`  
 vorgenommen Das Metadatentoken, das die Schnittstelle darstellt, die die implementierte Methode definiert.  

## <a name="remarks"></a>Hinweise

 Sie erhalten den Wert für `iImpl`, indem Sie die [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) -Methode aufrufen.
 
 Nehmen wir beispielsweise an, dass eine Klasse den `mdTypeDef` Tokenwert 0x02000007 aufweist und drei Schnittstellen implementiert, deren Typen über Token verfügen: 

- 0x02000003 (TypeDef)
- 0x0100000a (TypeRef)
- 0x0200001c (typedef)

Konzeptionell werden diese Informationen in einer Schnittstellen Implementierungs Tabelle wie folgt gespeichert:

| Zeilennummer | Class-Token | Schnittstellen Token |
|------------|-------------|-----------------|
| 4          |             |                 |
| 5          | 02000007    | 02000003        |
| 6          | 02000007    | 0100000A        |
| 7          |             |                 |
| 8          | 02000007    | 0200001C        |

Rückruf: das Token ist ein 4-Byte-Wert:

- Die unteren 3 Bytes enthalten die Zeilennummer oder RID.
- Das obere Byte enthält den Tokentyp – 0x09 für `mdtInterfaceImpl`.

`GetInterfaceImplProps` gibt die in der Zeile gespeicherten Informationen zurück, deren Token Sie im `iImpl`-Argument angeben. 
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
