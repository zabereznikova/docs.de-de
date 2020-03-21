---
title: IMetaDataImport::FindMember-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
ms.openlocfilehash: dab155b82d87609b3d3f390133e6490502a43518
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177280"
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember-Methode
Ruft einen Zeiger auf das MemberDef-Token für das Feld <xref:System.Type> oder die Methode ab, das von der angegebenen Datei eingeschlossen ist und über den angegebenen Namen und die angegebene Metadatensignatur verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 [in] Das TypeDef-Token für die Klasse oder Schnittstelle, die den zu suchenden Member einschließt. Wenn dieser `mdTokenNil`Wert ist, erfolgt die Suche nach einer global-variablen oder globalen Funktion.  
  
 `szName`  
 [in] Der Name des Elements, nach dem gesucht werden soll.  
  
 `pvSigBlob`  
 [in] Ein Zeiger auf die binäre Metadatensignatur des Members.  
  
 `cbSigBlob`  
 [in] Die Größe in `pvSigBlob`Bytes von .  
  
 `pmb`  
 [out] Ein Zeiger auf das übereinstimmende MemberDef-Token.  
  
## <a name="remarks"></a>Bemerkungen  
 Sie geben den Member mit seiner`td`einschließenden`szName`Klasse oder Schnittstelle (`pvSigBlob`), seinem Namen ( ) und optional seiner Signatur ( ) an. Möglicherweise gibt es mehrere Member mit demselben Namen in einer Klasse oder Schnittstelle. Übergeben Sie in diesem Fall die Signatur des Mitglieds, um die eindeutige Übereinstimmung zu finden.  
  
 Die übergebene `FindMember` Signatur muss im aktuellen Bereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind. Eine Signatur kann ein Token einbetten, das die einschließende Klasse oder den Werttyp identifiziert. Das Token ist ein Index in der lokalen TypeDef-Tabelle. Sie können keine Laufzeitsignatur außerhalb des Kontexts des aktuellen Bereichs erstellen `FindMember`und diese Signatur als Eingabe für die Eingabe für verwenden.  
  
 `FindMember`findet nur Member, die direkt in der Klasse oder Schnittstelle definiert wurden; Es werden keine geerbten Mitglieder gefunden.  
  
> [!NOTE]
> `FindMember`ist eine Hilfsmethode. Es ruft [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Wenn dieser Aufruf keine Übereinstimmung `FindMember` findet, ruft [iMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)auf.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
