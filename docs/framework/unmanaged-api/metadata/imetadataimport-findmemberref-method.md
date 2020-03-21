---
title: IMetaDataImport::FindMemberRef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
ms.openlocfilehash: d8b8bfd0e70e75c702f32555c10f433a1ff4ae10
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175420"
---
# <a name="imetadataimportfindmemberref-method"></a>IMetaDataImport::FindMemberRef-Methode
Ruft einen Zeiger auf das MemberRef-Token für den Memberverweis ab, der von der angegebenen <xref:System.Type> Datei eingeschlossen ist und über den angegebenen Namen und die angegebene Metadatensignatur verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `td`  
 [in] Das TypeRef-Token für die Klasse oder Schnittstelle, die den Memberverweis einschließt, nach dem gesucht werden soll. Wenn dieser `mdTokenNil`Wert ist, erfolgt die Suche nach einer globalen Variablen oder einem verweis auf globale Funktionen.  
  
 `szName`  
 [in] Der Name des Memberverweises, nach dem gesucht werden soll.  
  
 `pvSigBlob`  
 [in] Ein Zeiger auf die binäre Metadatensignatur des Memberverweises.  
  
 `cbSigBlob`  
 [in] Die Größe in `pvSigBlob`Bytes von .  
  
 `pmr`  
 [out] Ein Zeiger auf das übereinstimmende MemberRef-Token.  
  
## <a name="remarks"></a>Bemerkungen  
 Sie geben den Member mit seiner`td`einschließenden`szName`Klasse oder Schnittstelle (`pvSigBlob`), seinem Namen ( ) und optional seiner Signatur ( ) an.  
  
 Die übergebene `FindMemberRef` Signatur muss im aktuellen Bereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind. Eine Signatur kann ein Token einbetten, das die einschließende Klasse oder den Werttyp identifiziert. Das Token ist ein Index in der lokalen TypeDef-Tabelle. Sie können keine Laufzeitsignatur außerhalb des Kontexts des aktuellen Bereichs `FindMemberRef`erstellen und diese Signatur als Eingabe für verwenden.  
  
 `FindMemberRef`findet nur Memberverweise, die direkt in der Klasse oder Schnittstelle definiert wurden; Es werden keine geerbten Memberverweise gefunden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
