---
title: IMetaDataImport::FindField-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
ms.openlocfilehash: 842d6c0deb90bc45cb59454fb30fcc3544d742f1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437949"
---
# <a name="imetadataimportfindfield-method"></a>IMetaDataImport::FindField-Methode
Ruft einen Zeiger auf das FieldDef-Token für das Feld ab, das durch die angegebene <xref:System.Type> eingeschlossen ist und über den angegebenen Namen und die angegebene Metadatensignatur verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 in Das TypeDef-Token für die Klasse oder Schnittstelle, die das Feld einschließt, nach dem gesucht werden soll. Wenn dieser Wert `mdTokenNil`ist, wird die Suche für eine globale Variable durchgeführt.  
  
 `szName`  
 in Der Name des Felds, nach dem gesucht werden soll.  
  
 `pvSigBlob`  
 in Ein Zeiger auf die binäre Metadatensignatur des Felds.  
  
 `cbSigBlob`  
 in Die Größe `pvSigBlob`in Byte.  
  
 `pmb`  
 vorgenommen Ein Zeiger auf das übereinstimmende FieldDef-Token.  
  
## <a name="remarks"></a>Hinweise  
 Sie geben das Feld mit der einschließenden Klasse oder Schnittstelle (`td`), dem Namen (`szName`) und optional der Signatur (`pvSigBlob`) an.  
  
 Die an `FindField` über gegebene Signatur muss im aktuellen Gültigkeitsbereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind. Eine Signatur kann ein Token einbetten, das den einschließenden Klassen-oder Werttyp identifiziert. (Das Token ist ein Index in der lokalen Tabelle "Typedef"). Sie können keine Lauf Zeit Signatur außerhalb des Kontexts des aktuellen Bereichs erstellen und diese Signatur als Eingabe für `FindField`verwenden.  
  
 `FindField` findet nur Felder, die direkt in der Klasse oder Schnittstelle definiert wurden. geerbte Felder werden nicht gefunden.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
