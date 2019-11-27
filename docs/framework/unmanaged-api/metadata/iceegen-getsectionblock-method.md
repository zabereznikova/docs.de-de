---
title: ICeeGen::GetSectionBlock-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: 0731053fb37c775d25052a5fd99a479a44ff5862
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434878"
---
# <a name="iceegengetsectionblock-method"></a>ICeeGen::GetSectionBlock-Methode
Ruft einen Abschnitts Block der Codebasis ab.  
  
 Diese Methode ist veraltet und sollte nicht verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
## <a name="parameters"></a>Parameter  
 `section`  
 in Der Abschnitt, aus dem ein Block der Codebasis abgerufen wird.  
  
 `len`  
 in Die Länge des abzurufenden Blocks.  
  
 `align`  
 in Das Byte relativ zum Anfang des Abschnitts, mit dem das erste Byte des Blocks ausgerichtet werden soll. Dies ist die Position des-Blocks innerhalb des-Abschnitts.  
  
 `ppBytes`  
 vorgenommen Ein Zeiger auf einen Speicherort, der die Adresse des abgerufenen Blocks empfängt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie über besondere Abschnitts Anforderungen verfügen, die nicht von anderen Methoden behandelt werden, wenden Sie `GetSectionBlock` nur an.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICeeGen-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
