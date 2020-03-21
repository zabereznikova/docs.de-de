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
ms.openlocfilehash: 4b8ddf7fec12d175f030c0ea0ed982c6fb334aee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175381"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>IMetaDataImport::GetInterfaceImplProps-Methode
Ruft einen Zeiger auf die Metadatentoken für die ab, die <xref:System.Type> die angegebene Methode implementiert, und für die Schnittstelle, die diese Methode deklariert.
  
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
 [in] Das Metadatentoken, das die Methode darstellt, für die die Klassen- und Schnittstellentoken zurückgegeben werden sollen.  
  
 `pClass`  
 [out] Das Metadatentoken, das die Klasse darstellt, die die Methode implementiert.  
  
 `ptkIface`  
 [out] Das Metadatentoken, das die Schnittstelle darstellt, die die implementierte Methode definiert.  

## <a name="remarks"></a>Bemerkungen

 Sie erhalten den `iImpl` Wert für, indem Sie die [EnumInterfaceImpls-Methode](imetadataimport-enuminterfaceimpls-method.md) aufrufen.

 Angenommen, eine Klasse hat `mdTypeDef` den Tokenwert 0x02000007 und implementiert drei Schnittstellen, deren Typen Token haben:

- 0x02000003 (TypeDef)
- 0x0100000A (TypeRef)
- 0x0200001C (TypeDef)

Diese Informationen werden konzeptionell in einer Schnittstellenimplementierungstabelle gespeichert als:

| Zeilennummer | Klassentoken | Schnittstellentoken |
|------------|-------------|-----------------|
| 4          |             |                 |
| 5          | 02000007    | 02000003        |
| 6          | 02000007    | 0100000A        |
| 7          |             |                 |
| 8          | 02000007    | 0200001C        |

Rückruf, das Token ist ein 4-Byte-Wert:

- Die unteren 3 Bytes enthalten die Zeilennummer oder RID.
- Das obere Byte enthält den Tokentyp `mdtInterfaceImpl`– 0x09 für .

`GetInterfaceImplProps`gibt die in der Zeile gehaltenen `iImpl` Informationen zurück, deren Token Sie im Argument angeben.
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
