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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83dec9b6ed3b1e538e0f1b7d13a33b8bdbc1cf54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200804"
---
# <a name="imetadataimportgetmemberprops-method"></a>IMetaDataImport::GetMemberProps-Methode
Ruft ab, in den Metadaten für eine angegebenen Member-Definition, einschließlich Name, binäre Signatur und relative virtuelle Adresse des gespeicherten Informationen dem <xref:System.Type> Member vom angegebenen Metadatentoken verwiesen wird. Dies ist eine einfache Hilfsmethode: Wenn *mb* MethodDef, dann ist **GetMethodProps** aufgerufen, wenn *mb* ist ein FieldDef, **GetFieldProps** wird aufgerufen. Finden Sie unter diesen anderen Methoden für Details. 
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [in] Das Token, das Element zum Abrufen der zugehörigen Metadaten für verweist.  
  
 `pClass`  
 [out] Ein Zeiger auf das Metadatentoken, das die Klasse des Elements darstellt.  
  
 `szMember`  
 [out] Der Name des Elements.  
  
 `cchMember`  
 [in] Die Größe in Breitzeichen die `szMember` Puffer.  
  
 `pchMember`  
 [out] Die Größe in Breitzeichen der zurückgegebene Name.  
  
 `pdwAttr`  
 [out] Alle Flagwerte, die auf den Member angewendet wird.  
  
 `ppvSigBlob`  
 [out] Ein Zeiger auf die binäre Metadatensignatur des Elements.  
  
 `pcbSigBlob`  
 [out] Die Größe in Bytes der `ppvSigBlob`.  
  
 `pulCodeRVA`  
 [out] Ein Zeiger auf die relative virtuelle Adresse des Elements.  
  
 `pdwImplFlags`  
 [out] Alle Methodenimplementierungsflags, der dem Element zugeordnet wird.  
  
 `pdwCPlusTypeFlag`  
 [out] Ein Flag, das kennzeichnet eine <xref:System.ValueType>. Es ist eines der `ELEMENT_TYPE_*` Werte.
  
 `ppValue`  
 [out] Eine Zeichenfolgenkonstante, die von diesem Element zurückgegeben.  
  
 `pcchValue`  
 [out] Die Größe in Zeichen des `ppValue`, oder NULL, wenn `ppValue` errichtet keine Zeichenfolge.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
