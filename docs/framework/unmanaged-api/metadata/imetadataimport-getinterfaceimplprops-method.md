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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76e2ebbd47a5e36a722fce33ba67d7efb4db8675
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115933"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>IMetaDataImport::GetInterfaceImplProps-Methode
Ruft einen Zeiger auf das Metadatentoken für die <xref:System.Type> , der die angegebene Methode implementiert und für die Schnittstelle, die diese Methode deklariert.
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `iiImpl`  
 [in] Das Metadatentoken, das die Methode zum Zurückgeben von der Klassen- und Token für darstellt.  
  
 `pClass`  
 [out] Das Metadatentoken, das die Klasse, die Methode implementiert, darstellt.  
  
 `ptkIface`  
 [out] Das Metadatentoken, das die Schnittstelle, die die implementierte Methode definiert darstellt.  

## <a name="remarks"></a>Hinweise

 Rufen Sie den Wert für `iImpl` durch Aufrufen der [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) Methode.
 
 Nehmen wir beispielsweise an, dass eine Klasse verfügt über eine `mdTypeDef` token-Wert von 0 x 02000007 und, dass es drei Schnittstellen implementiert, deren Typen Token haben: 

- 0x02000003 (TypeDef)
- 0x0100000A (TypeRef)
- 0x0200001C (TypeDef)

Vom Konzept her ist diese Informationen in eine Schnittstellentabelle-Implementierung als gespeichert:

| Zeilennummer | Klassen-token | Interface-token |
|------------|-------------|-----------------|
| 4          |             |                 |
| 5          | 02000007    | 02000003        |
| 6          | 02000007    | 0100000A        |
| 7          |             |                 |
| 8          | 02000007    | 0200001C        |

Denken Sie daran, das Token ein 4-Byte-Wert ist:

- Die niederwertigen 3 Bytes enthalten die Nummer der Zeile, oder entfernen.
- Das obere Byte enthält den Tokentyp: 0 x 09 für `mdtInterfaceImpl`.

`GetInterfaceImplProps` Gibt die Informationen, in der Zeile, deren Token, das Sie bereitstellen gespeichert, in der `iImpl` Argument. 
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
