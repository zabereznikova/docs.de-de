---
title: ICeeGen::AddSectionReloc-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
ms.openlocfilehash: 129750644962cee3206b9e38cbeaa77d38dddd71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176109"
---
# <a name="iceegenaddsectionreloc-method"></a>ICeeGen::AddSectionReloc-Methode
Fügt der Codebasis eine .reloc-Anweisung hinzu.  
  
 Diese Methode ist veraltet und sollte nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `section`  
 [in] Der Abschnitt des In-Memory-Codes, dem eine .reloc-Anweisung hinzugefügt werden soll.  
  
 `offset`  
 [in] Der Offset des Abschnitts.  
  
 `relativeTo`  
 [in] Der Abschnitt, `offset` auf den sich bezieht.  
  
 `relocType`  
 [in] Einer der [CeeSectionRelocType-Werte,](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) der die Art der hinzuzufügenden .reloc-Anweisung angibt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICeeGen-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
