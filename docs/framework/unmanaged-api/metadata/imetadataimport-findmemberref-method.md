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
ms.openlocfilehash: 068014732cee91147edaec29fa0f954a741d8b5c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491653"
---
# <a name="imetadataimportfindmemberref-method"></a>IMetaDataImport::FindMemberRef-Methode
Ruft einen Zeiger auf das Mitgliedschaft Verweis Token für den Element Verweis ab, der durch den angegebenen eingeschlossen ist <xref:System.Type> und den angegebenen Namen und die angegebene Metadatensignatur aufweist.  
  
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
 in Das TypeRef-Token für die Klasse oder Schnittstelle, die den zu suchenden Element Verweis einschließt. Wenn dieser Wert ist `mdTokenNil` , erfolgt die Suche für eine globale Variable oder einen globalen Funktions Verweis.  
  
 `szName`  
 in Der Name des Element Verweises, nach dem gesucht werden soll.  
  
 `pvSigBlob`  
 in Ein Zeiger auf die binäre Metadatensignatur des Element Verweises.  
  
 `cbSigBlob`  
 in Die Größe von in Bytes `pvSigBlob` .  
  
 `pmr`  
 vorgenommen Ein Zeiger auf das übereinstimmende mitgliedlinienref-Token.  
  
## <a name="remarks"></a>Bemerkungen  
 Sie geben den Member mit der einschließenden Klasse oder Schnittstelle ( `td` ), dem Namen ( `szName` ) und optional der Signatur ( `pvSigBlob` ) an.  
  
 Die an über gegebene Signatur `FindMemberRef` muss im aktuellen Gültigkeitsbereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind. Eine Signatur kann ein Token einbetten, das den einschließenden Klassen-oder Werttyp identifiziert. Das Token ist ein Index in der lokalen Tabelle "Typedef". Sie können keine Lauf Zeit Signatur außerhalb des Kontexts des aktuellen Bereichs erstellen und diese Signatur als Eingabe für verwenden `FindMemberRef` .  
  
 `FindMemberRef`sucht nur Member-Verweise, die direkt in der Klasse oder Schnittstelle definiert wurden. vererbte Element Verweise werden nicht gefunden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [IMetaDataImport-Schnittstelle](imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](imetadataimport2-interface.md)
