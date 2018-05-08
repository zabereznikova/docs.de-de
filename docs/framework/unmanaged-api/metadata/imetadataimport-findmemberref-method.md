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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3736d604b7e77028a2b99d462d88ae207df926c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataimportfindmemberref-method"></a>IMetaDataImport::FindMemberRef-Methode
Ruft ein Zeiger auf das MemberRef-Token für das Element verweisen, d. h. durch das angegebene eingeschlossen <xref:System.Type> und den angegebenen Namen und Metadaten aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `td`  
 [in] Das TypeRef-Token für die Klasse oder Schnittstelle, die den Parameterverweis zu suchende einschließt. Wenn dieser Wert ist `mdTokenNil`, die Suche für eine globale Variable oder eine globale Funktion Verweis erfolgt.  
  
 `szName`  
 [in] Der Name des zu suchenden den Parameterverweis.  
  
 `pvSigBlob`  
 [in] Ein Zeiger auf die binäre Metadatensignatur der den Parameterverweis.  
  
 `cbSigBlob`  
 [in] Die Größe in Bytes des `pvSigBlob`.  
  
 `pmr`  
 [out] Ein Zeiger auf das übereinstimmende MemberRef-Token.  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie die Member, die mit der einschließenden Klasse oder Schnittstelle (`td`), seinen Namen (`szName`), und optional die Signatur (`pvSigBlob`).  
  
 Die Signatur zu übergeben, um `FindMemberRef` muss wurden im aktuellen Bereich generiert wurde, da Signaturen an einen bestimmten Bereich gebunden sind. Eine Signatur kann ein Token einbetten, die die einschließende Klasse oder der angegebene Werttyp identifiziert. Das Token ist ein Index in die lokale TypeDef-Tabelle. Sie können keine Laufzeit-Signatur im Kontext des aktuellen Gültigkeitsbereichs erstellen und verwenden Sie diese Signatur als Eingabe für `FindMemberRef`.  
  
 `FindMemberRef` Sucht nur Elementverweise, die direkt in der Klasse oder Schnittstelle definiert wurden. Es findet keine geerbten Member verweisen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
