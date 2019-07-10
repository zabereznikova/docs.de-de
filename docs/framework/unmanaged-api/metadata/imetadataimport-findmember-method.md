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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: caec760cea52cb14d3fdb5d4cf0b59adcae5633b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782515"
---
# <a name="imetadataimportfindmember-method"></a>IMetaDataImport::FindMember-Methode
Ruft einen Zeiger auf das MemberDef token für das Feld oder eine Methode, die eingeschlossen ist mit dem angegebenen <xref:System.Type> und dem angegebenen Namen und Metadaten aufweist.  
  
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
 [in] Die TypeDef-Token für die Klasse oder Schnittstelle, die zu suchenden Member einschließt. Wenn dieser Wert ist `mdTokenNil`, die Suche für eine globale Variable oder eine globale Funktion durchgeführt wird.  
  
 `szName`  
 [in] Der Name des zu suchenden Members.  
  
 `pvSigBlob`  
 [in] Ein Zeiger auf die binäre Metadatensignatur des Elements.  
  
 `cbSigBlob`  
 [in] Die Größe in Bytes der `pvSigBlob`.  
  
 `pmb`  
 [out] Ein Zeiger auf das entsprechende MemberDef-Token.  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie den Member, die mit der einschließenden Klasse oder Schnittstelle (`td`), seinen Namen (`szName`), und optional die Signatur (`pvSigBlob`). Es gibt möglicherweise mehrere Member mit demselben Namen in einer Klasse oder Schnittstelle. In diesem Fall übergeben Sie die Signatur des Members um die eindeutige Übereinstimmung zu finden.  
  
 Die Signatur, die an `FindMember` müssen wurden generiert im aktuellen Bereich, da die Signaturen für einen bestimmten Bereich gebunden sind. Eine Signatur kann es sich um ein Token einbetten, die die einschließende Klasse oder eines Werttyps identifiziert. Das Token ist ein Index in die lokale TypeDef-Tabelle. Sie erstellen eine Signatur zur Laufzeit im Kontext des aktuellen Bereichs und verwenden Sie diese Signatur als Eingabe können nicht `FindMember`.  
  
 `FindMember` Sucht nur Member, die direkt in der Klasse oder Schnittstelle definiert wurden. Es findet keine geerbte Member.  
  
> [!NOTE]
>  `FindMember` ist eine Hilfsmethode. Ruft [IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Wenn dieser Aufruf keine Übereinstimmung findet `FindMember` ruft dann [IMetaDataImport:: FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
