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
ms.openlocfilehash: e81816ce2194c2c1862cb997ad2c6e5baf301231
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703999"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>IMetaDataImport::GetInterfaceImplProps-Methode

Ruft einen Zeiger auf die Metadatentoken für den ab, der <xref:System.Type> die angegebene Methode implementiert, und für die-Schnittstelle, die diese Methode deklariert.
  
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

 Sie erhalten den Wert für, `iImpl` indem Sie die [EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md) -Methode aufrufen.

 Nehmen wir beispielsweise an, dass eine Klasse einen `mdTypeDef` Tokenwert von 0x02000007 aufweist und drei Schnittstellen implementiert, deren Typen über Token verfügen:

- 0x02000003 (typedef)
- 0x0100000a (TypeRef)
- 0x0200001c (typedef)

Konzeptionell werden diese Informationen in einer Schnittstellen Implementierungs Tabelle wie folgt gespeichert:

| Zeilennummer | Class-Token | Schnittstellen Token |
|------------|-------------|-----------------|
| 4          |             |                 |
| 5          | 02000007    | 02000003        |
| 6          | 02000007    | 0100000a        |
| 7          |             |                 |
| 8          | 02000007    | 0200001c        |

Rückruf: das Token ist ein 4-Byte-Wert:

- Die unteren 3 Bytes enthalten die Zeilennummer oder RID.
- Das obere Byte enthält den Tokentyp – 0x09 für `mdtInterfaceImpl` .

`GetInterfaceImplProps` Gibt die in der Zeile gespeicherten Informationen zurück, deren Token Sie im- `iImpl` Argument angeben.
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
