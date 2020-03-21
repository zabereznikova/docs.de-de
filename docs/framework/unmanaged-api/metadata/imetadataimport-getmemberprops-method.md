---
title: IMetaDataImport::GetMemberProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: 72e14ea0414ebdeb8f54a4bdef8ce5208fc8ef72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177228"
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps-Methode
Ruft Informationen ab, die in den Metadaten für eine angegebene Elementdefinition gespeichert <xref:System.Type> sind, einschließlich des Namens, der Binärsignatur und der relativen virtuellen Adresse des Elements, auf das durch das angegebene Metadatentoken verwiesen wird. Dies ist eine einfache Hilfsmethode: Wenn *mb* ein MethodDef ist, wird **GetMethodProps** aufgerufen; Wenn *mb* ein FieldDef ist, wird **GetFieldProps** aufgerufen. Weitere Informationen finden Sie unter diesen anderen Methoden.
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] ULONG             *pulCodeRVA,
   [out] DWORD             *pdwImplFlags,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `mb`  
 [in] Das Token, das auf das Mitglied verweist, für das die zugehörigen Metadaten abgerufen werden sollen.  
  
 `pClass`  
 [out] Ein Zeiger auf das Metadatentoken, das die Klasse des Members darstellt.  
  
 `szMember`  
 [out] Der Name des Mitglieds.  
  
 `cchMember`  
 [in] Die Größe in breiten `szMember` Zeichen des Puffers.  
  
 `pchMember`  
 [out] Die Größe des zurückgegebenen Namens in weiten Zeichen.  
  
 `pdwAttr`  
 [out] Alle Flagwerte, die auf das Element angewendet werden.  
  
 `ppvSigBlob`  
 [out] Ein Zeiger auf die binäre Metadatensignatur des Members.  
  
 `pcbSigBlob`  
 [out] Die Größe in `ppvSigBlob`Bytes von .  
  
 `pulCodeRVA`  
 [out] Ein Zeiger auf die relative virtuelle Adresse des Elements.  
  
 `pdwImplFlags`  
 [out] Alle Methodenimplementierungsflags, die dem Member zugeordnet sind.  
  
 `pdwCPlusTypeFlag`  
 [out] Ein Flag, <xref:System.ValueType>das eine markiert. Es ist einer `ELEMENT_TYPE_*` der Werte.
  
 `ppValue`  
 [out] Ein konstanter Zeichenfolgenwert, der von diesem Member zurückgegeben wird.  
  
 `pcchValue`  
 [out] Die Größe in `ppValue`Zeichen von `ppValue` , oder Null, wenn keine Zeichenfolge vorhanden ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
