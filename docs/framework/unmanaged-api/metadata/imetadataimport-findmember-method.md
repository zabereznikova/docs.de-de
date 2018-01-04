---
title: IMetaDataImport::FindMember-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMember
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a20930688aed210309a719de2c7187f1f5fd1f24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember-Methode
Ruft einen Zeiger auf das MemberDef token für das Feld oder eine Methode, die eingeschlossen ist durch das angegebene <xref:System.Type> und den angegebenen Namen und Metadaten aufweist.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `td`  
 [in] Das TypeDef-Token für die Klasse oder Schnittstelle, das der gesuchten Member enthält. Wenn dieser Wert `mdTokenNil`, wird die Suche für eine globale Variable oder eine globale Funktion durchgeführt.  
  
 `szName`  
 [in] Der Name des zu suchenden Elements.  
  
 `pvSigBlob`  
 [in] Ein Zeiger auf die binäre Metadatensignatur des Members.  
  
 `cbSigBlob`  
 [in] Die Größe in Bytes des `pvSigBlob`.  
  
 `pmb`  
 [out] Ein Zeiger auf das übereinstimmende MemberDef-Token.  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie die Member, die mit der einschließenden Klasse oder Schnittstelle (`td`), seinen Namen (`szName`), und optional die Signatur (`pvSigBlob`). Es gibt möglicherweise mehrere Elemente mit dem gleichen Namen in einer Klasse oder Schnittstelle. In diesem Fall übergeben Sie Signatur des Members, um die eindeutige Übereinstimmung zu finden.  
  
 Die Signatur zu übergeben, um `FindMember` muss wurden im aktuellen Bereich generiert wurde, da Signaturen an einen bestimmten Bereich gebunden sind. Eine Signatur kann ein Token einbetten, die die einschließende Klasse oder der angegebene Werttyp identifiziert. Das Token ist ein Index in die lokale TypeDef-Tabelle. Sie erstellen eine Laufzeit-Signatur im Kontext des aktuellen Gültigkeitsbereichs und verwenden Sie diese Signatur als Eingabe können nicht `FindMember`.  
  
 `FindMember`Sucht nur Member, die direkt in der Klasse oder Schnittstelle definiert wurden. geerbte Member werden nicht gefunden.  
  
> [!NOTE]
>  `FindMember`ist eine Hilfsmethode. Sie ruft [IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Wenn dieser Aufruf keine Übereinstimmung findet `FindMember` ruft dann [IMetaDataImport:: FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
