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
ms.openlocfilehash: 59512cc1c1b280d7fe6deb2f9d721ad53547e356
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437955"
---
# <a name="imetadataimportfindmemberref-method"></a>IMetaDataImport::FindMemberRef-Methode
Ruft einen Zeiger auf das Mitgliedschaft Verweis Token für den Element Verweis ab, der durch die angegebene <xref:System.Type> und den angegebenen Namen und die angegebene Metadatensignatur eingeschlossen ist.  
  
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
 in Das TypeRef-Token für die Klasse oder Schnittstelle, die den zu suchenden Element Verweis einschließt. Wenn dieser Wert `mdTokenNil`ist, erfolgt die Suche für eine globale Variable oder einen globalen Funktions Verweis.  
  
 `szName`  
 in Der Name des Element Verweises, nach dem gesucht werden soll.  
  
 `pvSigBlob`  
 in Ein Zeiger auf die binäre Metadatensignatur des Element Verweises.  
  
 `cbSigBlob`  
 in Die Größe `pvSigBlob`in Byte.  
  
 `pmr`  
 vorgenommen Ein Zeiger auf das übereinstimmende mitgliedlinienref-Token.  
  
## <a name="remarks"></a>Hinweise  
 Sie geben den Member mithilfe der einschließenden Klasse oder Schnittstelle (`td`), dessen Namen (`szName`) und optional dessen Signatur (`pvSigBlob`) an.  
  
 Die an `FindMemberRef` über gegebene Signatur muss im aktuellen Gültigkeitsbereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind. Eine Signatur kann ein Token einbetten, das den einschließenden Klassen-oder Werttyp identifiziert. Das Token ist ein Index in der lokalen Tabelle "Typedef". Sie können keine Lauf Zeit Signatur außerhalb des Kontexts des aktuellen Bereichs erstellen und diese Signatur als Eingabe für `FindMemberRef`verwenden.  
  
 `FindMemberRef` findet nur Member-Verweise, die direkt in der Klasse oder Schnittstelle definiert wurden. vererbte Element Verweise werden nicht gefunden.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
