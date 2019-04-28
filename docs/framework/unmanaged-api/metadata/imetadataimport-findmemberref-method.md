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
ms.openlocfilehash: abbd35fe390cc09951b762a5fd671d2d34a57c6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777883"
---
# <a name="imetadataimportfindmemberref-method"></a>IMetaDataImport::FindMemberRef-Methode
Ruft ein Zeiger auf das MemberRef-Token für das Element verweisen, eingeschlossen durch das angegebene <xref:System.Type> und dem angegebenen Namen und Metadaten aufweist.  
  
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
  
## <a name="parameters"></a>Parameter  
 `td`  
 [in] Die TypeRef-Token für die Klasse oder Schnittstelle, die den Parameterverweis zu suchende eingeschlossen werden soll. Wenn dieser Wert ist `mdTokenNil`, die Suche für eine globale Variable oder einen Verweis für die globale Funktion durchgeführt wird.  
  
 `szName`  
 [in] Der Name des Verweises zu suchende Element.  
  
 `pvSigBlob`  
 [in] Ein Zeiger auf die binäre Metadatensignatur der den Parameterverweis.  
  
 `cbSigBlob`  
 [in] Die Größe in Bytes der `pvSigBlob`.  
  
 `pmr`  
 [out] Ein Zeiger auf das entsprechende MemberRef-Token.  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie den Member, die mit der einschließenden Klasse oder Schnittstelle (`td`), seinen Namen (`szName`), und optional die Signatur (`pvSigBlob`).  
  
 Die Signatur, die an `FindMemberRef` müssen wurden generiert im aktuellen Bereich, da die Signaturen für einen bestimmten Bereich gebunden sind. Eine Signatur kann es sich um ein Token einbetten, die die einschließende Klasse oder eines Werttyps identifiziert. Das Token ist ein Index in die lokale TypeDef-Tabelle. Sie können keine Signatur zur Laufzeit im Kontext des aktuellen Bereichs und diese Signatur als Eingabe für `FindMemberRef`.  
  
 `FindMemberRef` Sucht nur Memberverweise, die direkt in der Klasse oder Schnittstelle definiert wurden. Es findet keine geerbte memberverweisen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
