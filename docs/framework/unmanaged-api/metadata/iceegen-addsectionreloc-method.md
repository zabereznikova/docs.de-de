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
ms.openlocfilehash: e5940f229e86b46bb8c5d5b2f9920a8261359f65
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436407"
---
# <a name="iceegenaddsectionreloc-method"></a>ICeeGen::AddSectionReloc-Methode
Fügt der Codebasis eine reloc-Anweisung hinzu.  
  
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
 in Der Abschnitt des in-Memory-Codes, dem eine reloc-Anweisung hinzugefügt werden soll.  
  
 `offset`  
 in Der Offset des Abschnitts.  
  
 `relativeTo`  
 in Der Abschnitt, auf den `offset` verweist.  
  
 `relocType`  
 in Einer der [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) -Werte, der die Art der hinzu zufügenden reloc-Anweisung angibt.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICeeGen-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
